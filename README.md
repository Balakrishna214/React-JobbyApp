# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh
`` bash npm install
``to install packages
``bash npm run dev`` to start project

 

# **React Job Search App**

This is a **Job Search App** built using **React.js** and integrated with RESTful APIs. It allows users to search for jobs, view job details, and filter jobs based on employment type and salary range. The app also includes authentication functionality to ensure secure access to job listings.

---

## **Table of Contents**

1. [Features](#features)
2. [Installation](#installation)
3. [Running the Project](#running-the-project)
4. [API Documentation](#api-documentation)
   - [Login API](#login-api)
   - [Profile API](#profile-api)
   - [Jobs API](#jobs-api)
   - [Job Details API](#job-details-api)
5. [Functionalities](#functionalities)
   - [Login Route](#login-route)
   - [Home Route](#home-route)
   - [Jobs Route](#jobs-route)
   - [Job Item Details Route](#job-item-details-route)
   - [Not Found Route](#not-found-route)
   - [Header](#header)
6. [Folder Structure](#folder-structure)
7. [Technologies Used](#technologies-used)
 

---

## **Features**

- **User Authentication**: Login functionality with JWT-based authentication.
- **Job Search**: Search for jobs by title, employment type, and salary range.
- **Job Details**: View detailed information about a specific job.
- **Filter Jobs**: Filter jobs by employment type (Full Time, Part Time, etc.) and salary range.
- **Responsive Design**: Works seamlessly on both desktop and mobile devices.

---

## **Installation**

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/job-search-app.git
   cd job-search-app
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```

4. Open your browser and navigate to `http://localhost:3000`.

---

## **API Documentation**

### **Login API**
- **URL**: `https://apis.ccbp.in/login`
- **Method**: `POST`
- **Request Body**:
  ```json
  {
    "username": "rahul",
    "password": "rahul@2021"
  }
  ```
- **Success Response**:
  ```json
  {
    "jwt_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
  ```
- **Failure Response**:
  ```json
  {
    "status_code": 404,
    "error_msg": "Username is not found"
  }
  ```

### **Profile API**
- **URL**: `https://apis.ccbp.in/profile`
- **Method**: `GET`
- **Response**:
  ```json
  {
    "profile_details": {
      "name": "John Doe",
      "profile_image_url": "https://example.com/profile.jpg",
      "short_bio": "Software Developer"
    }
  }
  ```

### **Jobs API**
- **URL**: `https://apis.ccbp.in/jobs`
- **Method**: `GET`
- **Query Parameters**:
  - `employment_type`: Comma-separated list of employment types (e.g., `FULLTIME,PARTTIME`).
  - `minimum_package`: Minimum salary package (e.g., `1000000` for 10 LPA).
  - `search`: Search query for job titles.
- **Response**:
  ```json
  {
    "jobs": [
      {
        "id": "bb95e51b-b1b2-4d97-bee4-1d5ec2b96751",
        "title": "Frontend Developer",
        "company_logo_url": "https://example.com/logo.png",
        "employment_type": "FULLTIME",
        "job_description": "We are looking for a skilled Frontend Developer...",
        "location": "Remote",
        "package_per_annum": "10 LPA"
      }
    ]
  }
  ```

### **Job Details API**
- **URL**: `https://apis.ccbp.in/jobs/:id`
- **Method**: `GET`
- **Response**:
  ```json
  {
    "job_details": {
      "id": "bb95e51b-b1b2-4d97-bee4-1d5ec2b96751",
      "title": "Frontend Developer",
      "company_logo_url": "https://example.com/logo.png",
      "employment_type": "FULLTIME",
      "job_description": "We are looking for a skilled Frontend Developer...",
      "location": "Remote",
      "package_per_annum": "10 LPA",
      "skills": [
        {
          "name": "React",
          "image_url": "https://example.com/react.png"
        }
      ],
      "life_at_company": {
        "description": "A great place to work...",
        "image_url": "https://example.com/life.jpg"
      }
    },
    "similar_jobs": [
      {
        "id": "cc95e51b-b1b2-4d97-bee4-1d5ec2b96752",
        "title": "Backend Developer",
        "company_logo_url": "https://example.com/logo.png",
        "employment_type": "FULLTIME",
        "job_description": "We are looking for a skilled Backend Developer...",
        "location": "Remote",
        "package_per_annum": "12 LPA"
      }
    ]
  }
  ```

---

## **Functionalities**

### **Login Route**
- Invalid credentials display an error message.
- Valid credentials navigate to the Home Route.
- Unauthenticated users are redirected to the Login Route when accessing protected routes.
- Authenticated users are redirected to the Home Route when accessing the Login Route.

### **Home Route**
- Authenticated users can navigate to the Jobs Route by clicking the "Find Jobs" button.

### **Jobs Route**
- Fetches and displays the user's profile and job listings.
- Supports filtering by employment type, salary range, and search query.
- Displays a loader while fetching data and shows an error message if the request fails.

### **Job Item Details Route**
- Fetches and displays detailed information about a specific job.
- Displays a list of similar jobs.
- Opens the company website in a new tab when the "Visit" button is clicked.

### **Not Found Route**
- Redirects users to a "Not Found" page for invalid URLs.

### **Header**
- Navigation links for Home, Jobs, and Logout functionality.
- Clicking the website logo navigates to the Home Route.

---

## **Folder Structure**

```
job-search-app/
├── public/
├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── App.js
│   ├── index.js
├── package.json
├── README.md
```

---

## **Technologies Used**

- **Frontend**: React.js
- **Routing**: React Router
- **Styling**: CSS
- **API Integration**: Fetch
- **Authentication**: JWT (JSON Web Tokens)

---
 
