# Blog App Django Backend

## Overview
This is the backend API for the blog application, built with Django and Django REST Framework. It provides endpoints to handle CRUD operations for blog posts, which can be accessed by the frontend React application.

Github link of Blog App React Frontend: https://github.com/chrisnumber49/Blog-App-React-Frontend

## Features
RESTful API: Built with Django REST Framework to handle CRUD operations for blog posts.

Authentication: Basic authentication is implemented to manage users.

Database: Uses SQLite (default) for storing blog posts. It can be switched to other databases like PostgreSQL if needed.

## Technologies Used
Django for backend development.

Django REST Framework for building the API.

SQLite for local database storage.

## Project Screen Shots
<img src="https://github.com/chrisnumber49/DjangoBlogAppBackend/blob/master/screen%20shot/demo1.PNG" width="700" > 
<img src="https://github.com/chrisnumber49/DjangoBlogAppBackend/blob/master/screen%20shot/demo2.PNG" width="700" > 
<img src="https://github.com/chrisnumber49/DjangoBlogAppBackend/blob/master/screen%20shot/demo3.PNG" width="700" > 

## Installation and Setup Instructions

Clone down this repository. You will need `Django` and `Django Rest Framework` installed globally on your machine.  

Installation: `pip install Django` and `pip install djangorestframework`

Creating new migrations: `python manage.py makemigrations`

Applying migrations: `python manage.py migrate`

To Start Server: `python manage.py runserver`  
 
To Visit App: `localhost:8000/`

## API Endpoints

GET /api/posts/ - Fetch all blog posts.

GET /api/posts/{id}/ - Fetch a single blog post by ID.

POST /api/posts/ - Create a new blog post.

PUT /api/posts/{id}/ - Update an existing blog post.

DELETE /api/posts/{id}/ - Delete a blog post by ID.


GET /api/comments/ - Fetch all comments left in all different posts.

POST /api/comments/ - Create a new comment in a specific blog post.

DELETE /api/comments/{id}/ - Delete a comment by ID.

## Usage

The backend exposes RESTful APIs for handling blog posts and comments. This API can be consumed by the front-end application to display and manage blog data and media.

## Reflection 

This is my first side project of integrating full-stack development with React frontend and Django backend. In the Django backend, I built a REST API for a blog application. In the database, we have 3 Models mapped to each single table: **Post**, **User**, and **Comment**. In the **Post** Model, the author field has many to one relationship with **User** Model; Identically, **Comment** Model also has many to one relationship with **User** Model and **Post** Model in its author and post field, that means one single post will contain an author of the post and also might have few post comments inside. Through the setting of serializers and URL routers, we can send requests to the specific URL to implement the CRUD operation and search any post with a specific keyword from the front-end interface.

I started this project by using the command `django-admin startproject` to create the boilerplate of the project, then create a new app with the command `python manage.py startapp`, two dependencies were installed, `pillow` is for for saving and serving static files to the client, and `django-cors-headers` is to allow resources to be accessed on other domains.

In the backend REST API of this side project, I learned about the concept of various components that make up REST framework, and understood each wrapper that Django Rest Framework provides for Views including function-based API Views, class-based API Views, GenericAPIView, viewsets, GenericViewSet and ModelViewSet, and lastly knew the Authentication and Permissions to restrict who can access the data.
