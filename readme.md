# 28-2nd-Wegabox-backend

- [**Megabox**](https://www.megabox.co.kr/) is a movie-ticketing site.
- This project focuses on the site's core features — browsing movie information and booking tickets.

</br>

## Team & timeline
- Period: 2022-01-10 ~ 2022-01-21
- Front-end: [Wegabox frontend GitHub repository](https://github.com/wecode-bootcamp-korea/28-2nd-Wegabox-frontend)
- Back-end: Minsung Kang, Minwook Jang

</br>


## Demo
- [Demo video (download link)](https://drive.google.com/file/d/1VEoUUSFTfd--QTRzeEnlRnOCLVZ2fl57/view?usp=sharing)
- [Wegabox project link](http://54.144.54.249:8000)

</br>


## Collaboration tools
- Slack
- GitHub
- Trello

</br>


## Tech stack
- Language: Python 3
- Framework: Django
- Database: MySQL
- Infra: AWS (EC2), RDS

</br>


## ERD
A compact implementation centered on the core features.
![ERD](https://user-images.githubusercontent.com/83395303/150482436-918b12f6-6c04-47f0-a4ca-2ca22c7eaa6a.png)

</br>


## Features
### Minsung Kang
Social login, ticket booking

</br>


#### User
##### Social login (Kakao)
- Request user info from the Kakao API using the access_token received from the frontend.
- Check whether the fetched user exists in the DB, and either register them via `get_or_create` or load the existing user.
- Issue a JWT token with the user's PK (primary key) as the payload.
- Login decorator: a decorator that decodes the JWT token, used wherever login is required.

</br>


#### Ticketing
##### Booking
- Use `Q` objects to filter different data based on the user's selected options (screening date, movie, region, theater) and return it to the frontend.
- When a screening schedule is selected, create a booking record from the user id obtained via the decorator and the selected schedule id.

</br>


### Minwook Jang
Main page & movie list page, AWS

</br>


#### Movie
- Use `Q` objects so users can view the full movie list or only currently-released films.
- Use `annotate` to add a booking-rate column to the table, letting users see now-showing movies ordered by booking rate (descending).

</br>


#### AWS (EC2, RDS)
- Set up EC2 and RDS and completed deployment.
- Ran the service in the background via a daemon.

</br>


## Reference
- This project was built for learning purposes, referencing the [**Megabox**](https://www.megabox.co.kr/) site.
- Although it is a production-grade project, it was made for study; using this code for profit or redistributing it without permission may cause legal issues.
- Most images used in this project were purchased by wecode and may not be used by anyone outside this project.
