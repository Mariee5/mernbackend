# WEDESIGN - Interior Design Website

A full-stack web application for an interior design company built with Express.js, Handlebars, and MongoDB. This project serves as both the backend API and server-side rendered frontend for a modern interior design business website.

## 🎨 Project Overview

WEDESIGN is a professional interior design company website that showcases services, portfolio, client testimonials, and provides a user registration system for booking quotations. The application features a beautiful, modern UI with responsive design, interactive elements, and seamless user experience.

## 📸 Screenshots

### Homepage Views

![Homepage 1](./screenshots/Screenshot%202025-11-05%20201408.png)

*Main homepage featuring hero section with "Designing Dreams, Creating Realities" tagline*

![Homepage 2](./screenshots/Screenshot%202025-11-05%20201445.png)

*Services and portfolio section showcasing interior design services*

### Registration Form

![Registration Form](./screenshots/Screenshot%202025-11-05%20201514.png)

*User registration page for booking quotations with form validation*

### Map View

![Map View](./screenshots/Screenshot%202025-11-05%20201537.png)

*Interactive map view showing company location using Leaflet.js*

## ✨ Key Features

- **Modern, Responsive UI**: Beautiful design with smooth animations and transitions
- **Server-Side Rendering**: Handlebars templates for SEO-friendly pages
- **User Registration System**: Secure user registration with password hashing
- **Portfolio Gallery**: Showcase of interior design projects
- **Client Testimonials**: Video and text testimonials from satisfied clients
- **Interactive Map**: Leaflet.js integration for location display
- **Service Showcase**: Detailed information about interior design services
- **Form Validation**: Input validation using express-validator

## 🛠️ Tech Stack

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **bcrypt** - Password hashing
- **express-validator** - Input validation

### Frontend
- **Handlebars (hbs)** - Server-side templating engine
- **Bootstrap 5** - CSS framework
- **Tailwind CSS** - Utility-first CSS framework
- **Leaflet.js** - Interactive maps
- **Slick Carousel** - Image carousel
- **Font Awesome** - Icons
- **Custom CSS** - Styling and animations

## 📁 Project Structure

```
mernbackend-main/
├── public/
│   ├── images/          # Static images and assets
│   └── style.css        # Main stylesheet
├── src/
│   ├── app.js           # Express server and routes
│   ├── db/
│   │   └── conn.js      # MongoDB connection
│   └── models/
│       └── user.js      # User model schema
├── templates/
│   ├── partials/
│   │   ├── header.hbs   # Header partial
│   │   └── navbar.hbs   # Navigation bar partial
│   └── views/
│       ├── index.hbs    # Homepage
│       ├── map.hbs      # Map view
│       └── registration.hbs  # Registration form
├── screenshots/         # Project screenshots
└── package.json         # Dependencies and scripts
```

## 📋 Requirements

### System Requirements

- **Node.js**: v14.0.0 or higher (v16+ recommended)
- **npm**: v6.0.0 or higher (comes with Node.js)
- **MongoDB**: v5.0 or higher (or use Docker)
- **Git**: For cloning the repository

### Node.js Dependencies

All dependencies are automatically installed when you run `npm install`. Here's the complete list:

#### Production Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| `express` | ^4.21.0 | Web application framework |
| `mongoose` | ^8.6.3 | MongoDB object modeling |
| `hbs` | ^4.2.0 | Handlebars templating engine |
| `bcrypt` | ^5.1.1 | Password hashing |
| `express-validator` | ^7.2.0 | Input validation middleware |

#### Development Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| `nodemon` | ^3.1.7 | Auto-restart server during development |

### External Services

- **MongoDB Database**: Required for user registration and data persistence
  - Local installation: MongoDB Community Server
  - Or use Docker: `mongo:6.0` image

### Browser Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled
- HTML5 support

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have the following installed:

- Node.js (v14 or higher) - [Download](https://nodejs.org/)
- MongoDB (local installation or Docker) - [Download](https://www.mongodb.com/try/download/community)
- npm (comes with Node.js) or yarn
- Git (for cloning) - [Download](https://git-scm.com/)

### Installation

1. **Clone the repository:**

```bash
git clone https://github.com/Mariee5/mernbackend.git
cd mernbackend
```

2. **Install dependencies:**

```bash
npm install
```

3. **Set up MongoDB:**

**Option A: Using Docker (Recommended)**

```bash
docker run -d --name mern-mongo -p 27017:27017 -v mern_mongo_data:/data/db mongo:6.0
```

**Option B: Local MongoDB Installation**

Ensure MongoDB is installed and running on `mongodb://localhost:27017`

4. **Start the development server:**

```bash
npm run dev
```

The server will start on `http://localhost:3001/` with nodemon for automatic reloading.

## 📝 API Endpoints

### GET Routes

- `GET /` - Renders homepage (index.hbs)
- `GET /map` - Renders map view (map.hbs)
- `GET /registration` - Renders registration form (registration.hbs)

### POST Routes

- `POST /user` - Creates a new user account

**Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "confirmPassword": "password123",
  "dob": "1990-01-01"
}
```

**Response (Success - 201):**
```json
{
  "message": "User created"
}
```

**Response (Error - 400/401/500):**
```json
{
  "errors": [...],
  "message": "Error message"
}
```

## 🔧 Configuration

### Database Connection

The application connects to MongoDB at:
- **Database Name**: `Interior`
- **Connection String**: `mongodb://localhost:27017/Interior`

To change the database connection, edit `src/db/conn.js`:

```javascript
mongoose.connect("mongodb://localhost:27017/Interior")
```

### Server Port

The server runs on port `3001` by default. To change it, set the `PORT` environment variable:

```bash
PORT=3000 npm run dev
```

## 🔒 Security Features

- **Password Hashing**: Passwords are hashed using bcrypt (10 salt rounds)
- **Input Validation**: All user inputs are validated using express-validator
- **Email Uniqueness**: Prevents duplicate email registrations
- **Password Confirmation**: Ensures passwords match before registration

## 🎯 Features Detail

### Homepage Sections

1. **Hero Section**: Eye-catching banner with call-to-action
2. **About Us**: Company information and values
3. **Why Choose Us**: Feature highlights with icons
4. **Services**: Space planning, renovation, and outdoor design
5. **Portfolio Gallery**: Showcase of completed projects
6. **Client Reviews**: Video and text testimonials
7. **Footer**: Social media links and company info

### User Registration

- Form validation for all fields
- Email format validation
- Password strength requirements (minimum 6 characters)
- Password confirmation matching
- Date of birth validation
- Duplicate email prevention

## 🐛 Troubleshooting

### Common Issues

**Port already in use:**
```bash
# Change PORT environment variable
PORT=3000 npm run dev
# Or stop the process using the port
```

**MongoDB connection error:**
- Ensure MongoDB is running on `localhost:27017`
- Check if the database name is correct
- Verify MongoDB service is started

**Missing dependencies:**
```bash
npm install
```

**Nodemon not restarting:**
- Ensure file extensions are correct (`.js`, `.hbs`)
- Check nodemon configuration in `package.json`

## 📦 Scripts

- `npm run dev` - Start development server with nodemon
- `npm test` - Run tests (not configured)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 👤 Author

**Mariee5**

- GitHub: [@Mariee5](https://github.com/Mariee5)

## 🙏 Acknowledgments

- Bootstrap for the responsive framework
- Leaflet.js for map functionality
- Font Awesome for icons
- All clients who provided testimonials

---

⭐ If you found this project helpful, please consider giving it a star!
