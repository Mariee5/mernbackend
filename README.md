# WEDESIGN — Interior Design Website

A full-stack web application for an interior design company combining an Express.js backend with Handlebars server-side rendering. It features portfolio showcases, user registration, and interactive elements with MongoDB integration for data persistence.

## Features

- Server-side rendered pages with Handlebars templates
- User registration with password hashing and validation
- Interactive portfolio gallery with smooth animations
- Client testimonials (video and text)
- Interactive map integration (Leaflet.js)
- Responsive design with Bootstrap and Tailwind CSS

## Project Structure

- **Backend (Express.js)**: `src/app.js`, `src/db/conn.js`, and `src/models/user.js`
- **Templates (Handlebars)**: `templates/views/` (index.hbs, map.hbs, registration.hbs) and `templates/partials/`
- **Static Assets**: `public/images/` and `public/style.css`

## Quick Start

### Install Dependencies

npm install### Start Development Server

npm run devThe server will run on `http://localhost:3001/` with nodemon for automatic reloading.

### MongoDB Setup

**Option A: Using Docker (Recommended)**

docker run -d --name mern-mongo -p 27017:27017 -v mern_mongo_data:/data/db mongo:6.0**Option B: Local MongoDB**

Ensure MongoDB is installed and running on `mongodb://localhost:27017`

## Screenshots

> Images are stored in `screenshots/` and referenced directly.

![Homepage](./screenshots/Screenshot%202025-11-05%20201408.png)

![Services](./screenshots/Screenshot%202025-11-05%20201445.png)

![Registration](./screenshots/Screenshot%202025-11-05%20201514.png)

![Map View](./screenshots/Screenshot%202025-11-05%20201537.png)

## How It Was Built

- **Backend** built with Express.js (`src/app.js`), MongoDB connection in `src/db/conn.js`, and user model in `src/models/user.js`
- **Frontend** templating with Handlebars (hbs) in `templates/views/` and partials in `templates/partials/`
- **Styling** through Bootstrap 5, Tailwind CSS, and custom CSS (`public/style.css`)
- **Dependencies**: mongoose for MongoDB, bcrypt for password hashing, express-validator for form validation
- **Development**: nodemon for auto-restart during development

## API Endpoints

- `GET /` - Homepage
- `GET /map` - Interactive map view
- `GET /registration` - User registration form
- `POST /user` - Create new user account (with validation)

## Notes

- MongoDB database name: `Interior`
- Default port: `3001` (configurable via `PORT` environment variable)
- Images are stored in `public/images/` and served as static assets
- Node modules are excluded from version control

## License

ISC License
