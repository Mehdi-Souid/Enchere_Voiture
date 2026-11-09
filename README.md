# Enchère Voiture: Car Auction Platform

A full-stack MERN web app where users sign up, publish car listings with a cover photo and a rich-text description, and browse or edit listings.

## Features

- **Authentication:** registration and login with bcrypt-hashed passwords and a JWT stored in an HTTP-only cookie
- **Listings:** create, edit and view car posts (title, summary, rich-text content, cover image)
- **Image upload:** cover photos are uploaded with Multer and served by the API
- **Ownership:** only the author of a listing can edit it
- **Feed:** latest listings first, each with its author and publication date

## Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | React 18, React Router, React Quill (rich-text editor), date-fns |
| Backend | Node.js, Express, Multer, cookie-parser, CORS |
| Auth | JSON Web Tokens, bcryptjs |
| Database | MongoDB with Mongoose |

## API

| Method | Route | Description |
|---|---|---|
| POST | `/register` | Create an account |
| POST | `/login` | Log in and receive the auth cookie |
| GET | `/profile` | Current user from the cookie |
| POST | `/logout` | Clear the auth cookie |
| POST | `/post` | Create a listing (multipart, with cover image) |
| PUT | `/post` | Update a listing (author only) |
| GET | `/post` | Latest listings |
| GET | `/post/:id` | One listing with its author |

## Getting Started

```bash
# Backend
npm install
cp api/.env.example api/.env   # then fill in MONGO_URI and JWT_SECRET
cd api && node index.js         # API on http://localhost:4000

# Frontend (in another terminal)
cd client
npm install
npm start                       # http://localhost:3000
```

## Project Structure

```
api/       Express API: routes, Mongoose models (User, Post), uploads/
client/    React app: pages (Index, Login, Register, Create/Edit/Post), Editor, Header
```
