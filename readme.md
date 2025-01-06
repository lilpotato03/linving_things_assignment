
# Task Management App

## Overview
The **Task Management App** is an internship assignment developed for **Living Things**. This project is a full-stack application that allows users to manage tasks with features such as authentication, task CRUD operations, and a responsive user interface.

### Project Structure

- **frontend/**: This is the client-side application built with **Vite** and **React**.
- **backend1/**: This is the authentication server built with **Node.js**.
- **backend2/**: This is the CRUD server built with **Django**.

Each of these directories is a separate submodule in the repository, meaning each component is in its own repository. 

---

## Cloning the Repository

### 1. Clone the repository with submodules:
To clone this repository and initialize the submodules, follow the steps below:

```bash
git clone --recurse-submodules <repository_url>
```


After cloning, navigate into each folder (`frontend`, `backend1`, and `backend2`) to set them up individually.

---

## Frontend Setup (Vite/React)

### 1. Navigate to the `frontend/` directory:
```bash
cd frontend
```

### 2. Install the necessary dependencies:
```bash
npm install
```

### 3. Run the development server:
```bash
npm run dev
```


---

## Backend1 Setup (Node.js - Authentication Server)

### 1. Navigate to the `backend1/` directory:
```bash
cd backend1
```

### 2. Install the necessary dependencies:
```bash
npm install
```

### 3. Set up environment variables:
Create a `.env` file in the root of the `backend1/` directory and add the following environment variables:

```
PORT=3000  # The port where the authentication server will run
DB_SECRET=<your_jwt_secret>  # A secret used for signing JWT tokens
```

### 4. Run the authentication server:
```bash
npm start
```

The authentication server will now run on the port defined in the `.env` file (default is `5000`).

---

## Backend2 Setup (Django - CRUD Server)

### 1. Navigate to the `backend2/` directory:
```bash
cd backend2
```

### 2. Create a virtual environment:
```bash
python3 -m venv venv
```

### 3. Activate the virtual environment:
- On Linux/macOS:
  ```bash
  source venv/bin/activate
  ```
- On Windows:
  ```bash
  venv\Scripts\activate
  ```

### 4. Install the necessary dependencies from `requirements.txt`:
```bash
pip install -r requirements.txt
```



### 5. Migrate the database:
```bash
python manage.py migrate
```

### 6. Run the Django server:
```bash
python manage.py runserver
```

By default, the Django application will run on `http://localhost:8000`.

---

## Vite Configuration (Frontend Proxy)

To make sure the frontend communicates correctly with the backend services, you need to set up the proxy configuration in the `vite.config.js` file inside the `frontend/` folder.

1. Open the `vite.config.js` file.

2. Ensure the proxy configuration is set to forward API requests to the correct backend servers. For example:

```js
export default {
  server: {
    proxy: {
      '/nodejs': 'http://localhost:3000',  // Proxy to backend1 (Authentication)
      '/django/api': 'http://localhost:8000', // Proxy to backend2 (CRUD)
    }
  }
}
```

Make sure to replace the `localhost` addresses and ports with the appropriate values for your setup.

---



