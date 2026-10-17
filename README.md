# Cars Dealership Full-Stack Capstone

**Repository name:** xrwvm-fullstack_developer_capstone

**Project name:** Cars Dealership - Full-Stack Web Application

A full-stack web application for a national car retailer in the United States. Visitors can browse dealerships, filter them by state, read and post dealer reviews, and sign up or log in to leave their own review.

## Technologies

- **Frontend:** React and Bootstrap, served by Django (static pages: Home, About Us and Contact Us)
- **Backend:** Django (authentication and REST endpoints), Express.js with MongoDB (dealerships and reviews), and a Flask sentiment analyzer microservice
- **Deployment:** Docker, Kubernetes and IBM Cloud Code Engine, with CI/CD through GitHub Actions

## Project structure

| Path | Purpose |
| --- | --- |
| `server/djangoapp` | Django views, URLs and REST API helpers (login, logout, register, dealers and reviews) |
| `server/djangoproj` | Django project settings and URL configuration |
| `server/database` | Express and MongoDB service for dealerships and reviews |
| `server/frontend/static` | Static pages: `Home.html`, `About.html` and `Contact.html` |
| `server/frontend/src` | React components: Login, Register, Dealers and Header |

## Running the Django server

```bash
cd server
pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

## Useful endpoints

| Endpoint | Description |
| --- | --- |
| `POST /djangoapp/login` | Log in with a username and password |
| `GET /djangoapp/logout` | Log out the current user |
| `POST /djangoapp/register` | Register a new user |
| `GET /fetchDealers` | All dealerships (Express service, port 3030) |
| `GET /fetchDealers/:state` | Dealerships in a state |
| `GET /fetchDealer/:id` | One dealership by id |
| `GET /fetchReviews/dealer/:id` | Reviews for a dealership |
