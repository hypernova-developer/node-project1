# Simple Watch Store

A full-stack Node.js web application for managing a watch store product catalog. Users can add products with images and prices, view them in a responsive grid layout, and delete products as needed.

---

## Features

- Product creation with image upload and price entry
- Product listing displayed in a responsive card grid
- Product deletion via AJAX with no page reload required
- MySQL database integration for persistent data storage
- Static file serving for uploaded images

---

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express 5
- **Database:** MySQL (via mysql2)
- **File Uploads:** Multer
- **Environment Variables:** dotenv
- **Frontend:** Plain HTML, CSS, and JavaScript

---

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Node.js](https://nodejs.org/) (v18 or later recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [MySQL](https://www.mysql.com/) database server (or a cloud-hosted MySQL instance)

---

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/node-project1.git
cd node-project1
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root with your MySQL connection string:

```env
MYSQL_PUBLIC_URL=mysql://username:password@host:port/database
```

### 4. Set up the database table

Connect to your MySQL instance and run the following SQL command to create the required `posts` table:

```sql
CREATE TABLE posts (
  id INT AUTO_INCREMENT PRIMARY KEY,
  image VARCHAR(255),
  caption VARCHAR(255)
);
```

### 5. Create the uploads directory

The application stores uploaded images in `public/uploads/`. This folder will be created automatically when the first image is uploaded, but you can create it manually to ensure it exists:

```bash
mkdir -p public/uploads
```

### 6. Start the application

```bash
npm start
```

The server will start on port `3000` by default. Navigate to `http://localhost:3000` in your browser to access the application.

---

## Usage

1. **Add a product:** Use the form at the top of the page to upload an image and enter a price.
2. **View products:** All products are displayed in a grid layout below the form.
3. **Delete a product:** Click the "Delete" button on any product card to remove it.

---

## Project Structure

```
node-project1/
├── public/
│   ├── index.html          # Frontend HTML page
│   └── uploads/            # Directory for uploaded product images
├── .env                    # Environment variables (MYSQL_PUBLIC_URL)
├── .gitignore              # Git ignore rules
├── package.json            # Project metadata and dependencies
├── package-lock.json       # Dependency lock file
├── server.js               # Main application entry point (Express server)
└── README.md               # Project documentation (this file)
```

---

## API Endpoints

| Method   | Endpoint        | Description                         |
|----------|-----------------|-------------------------------------|
| `GET`    | `/`             | Serves the frontend HTML page       |
| `GET`    | `/posts`        | Returns all products as JSON        |
| `POST`   | `/create`       | Creates a new product (multipart)   |
| `DELETE` | `/delete/:id`   | Deletes a product by its ID         |

---

## Contributing

Contributions are welcome. Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Make your changes and test them thoroughly.
4. Submit a pull request with a clear description of the changes.

---

## License

This project is licensed under the MIT License. See the [`LICENSE`](./LICENSE) file for more information.

## Maintainer

Maintained by [Arnold R Paghunasan](https://github.com/arnoldpaghunasan00-beep).
