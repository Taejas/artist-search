# Artist Search Web App

Artist Search is a full-stack web application for searching artists, exploring artworks, managing favorites, and user authentication. It is built using **MongoDB**, **Express.js**, **Angular**, **Node.js** (MEAN stack), and integrated with the [`Artsy API`](https://developers.artsy.net/), with responsive design using **Bootstrap**.

_This project was created as part of the CSCI 571: Web Technologies course at USC in the Spring 2025 semester. As per the instructor’s request, I have not shared the source code here to avoid plagiarism in future offerings of the course. If you are a recruiter and would like access to the code, please reach out to me directly._


## 📑 Table of Contents

1. [🎬 Demo Video](#-demo-video)
2. [🧩 Features](#-features)
   - [🔎 Artist Search](#-artist-search)
   - [👨‍🎨 Artist Details](#-artist-details)
   - [⭐ Favorites](#-favorites)
   - [🔑 Authentication](#-authentication)
3. [📡 Backend API Response Example](#-backend-api-response-example)
4. [📇 MongoDB Atlas Collection Format](#-mongodb-atlas-collection-format)
5. [🧰 Summary of Tools and Technologies](#-summary-of-tools-and-technologies)
6. [📱 Android App](#-android-app)


## 🎬 Demo Video

The following is a complete walkthrough of the Artist Search web app, showcasing all core features and functionality, including **artist search**, **details view**, **artworks**, **categories**, **favorites management**, **authentication**, and **toast notifications**.

https://github.com/user-attachments/assets/f7a4c1ef-79f3-4dd5-ab12-a386fa444536


## 🧩 Features

### 🔎 Artist Search

Users can initiate search by entering an artist's name and clicking the "Search" button or pressing the enter key. The frontend makes an AJAX call to the backend proxy, sending the input text. The backend makes a request to the Artsy server using the [`Search API`](https://developers.artsy.net/v2/docs/search), and the response is shown as a list of Bootstrap cards.

https://github.com/user-attachments/assets/33fe81a5-1ed3-4e24-ad7e-a11f2fb0e139


### 👨‍🎨 Artist Details

Clicking on an artist card opens the artist's details. This in turn consists of two tabs &ndash; "Artist info" and "Artworks".

#### Artist Info and Similar Artists

The "Artist info" tab includes the artist's name, birth and death years, nationality, and biography, as retrieved via the [`Artists API`](https://developers.artsy.net/v2/docs/artists). For authenticated users, there is a "Similar Artists" block, also implemented using Bootstrap cards.

#### Artworks and Categories

The "Artworks" tab contains the artworks of the selected artists, retrieved from the [`Artworks API`](https://developers.artsy.net/v2/docs/artworks). Clicking the "View categories" button opens a "Categories" modal for the corresponding artwork, which calls the [`Genes API`](https://developers.artsy.net/v2/docs/genes).

https://github.com/user-attachments/assets/4dc8ff39-cf5f-4bc6-897e-5c3e75ec62e3


### ⭐ Favorites

For authenticated users, a star-shaped "Favorites" button is shown on each artist card and next to the artist's name under "Artist info". Clicking the button toggles the state by adding/removing the artist to/from favorites. This information is stored along with other user details in MongoDB. The favorites cards can be accessed via the header bar, and are displayed in reverse chronological order (newest first) along with an interactive timer.

https://github.com/user-attachments/assets/1336b08c-5644-46dc-9568-126920ed3a5a


### 🔑 Authentication

**Register**, **login**, **logout** and **delete account** are implemented via the use of cookies and JSON Web Tokens, with validation both on the frontend and backend. In addition, [`Gravatar`](https://docs.gravatar.com/api/avatars/images/) is used for displaying the profile image of the user.

https://github.com/user-attachments/assets/cc1eb1d7-fca1-48f3-ab06-37bf6d760c92


## 📡 Backend API Response Example

The following screenshot shows part of the JSON response returned by the backend when searching for "Picasso":
<p align="center">
  <img src="https://github.com/user-attachments/assets/9a411b7b-21c4-4828-a1df-6a390262fe6a" alt="Backend API Response">
  <em>JSON response from the backend (proxying the Artsy API)</em>
</p>


## 📇 MongoDB Atlas Collection Format

The MongoDB ``users`` collection stores registered user data, including hashed passwords, profile image URLs (via Gravatar), and favorites. The following is a sample document structure:

<p align="center">
  <img src="https://github.com/user-attachments/assets/22fc50cd-1078-414f-b92b-ca9eb833c94e" alt="MongoDB Users Collection">
  <em>User data stored in a MongoDB Atlas collection</em>
</p>


## 🧰 Summary of Tools and Technologies

* **Backend**: Node.js, Express.js, MongoDB Atlas
* **Frontend**: Angular, TypeScript, HTML, CSS, Bootstrap, AJAX (HttpClientModule)
* **API integration**: Artsy API (Authentication, Search, Artists, Artworks, Genes)
* **Data format**: JSON (REST API communication)
* **Authentication**: JWT, HTTP-only cookies, bcrypt, Gravatar
* **Notifications**: Bootstrap Toasts
* **Testing tools**: Postman
* **Deployment**: Google Cloud Platform


## 📱 Android App

An Android version of this app, built using **Kotlin**, **Jetpack Compose**, **Retrofit**, and **Coil**, is available here: [Artist Search Android App](https://github.com/Taejas/artist-search-android)
