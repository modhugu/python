# Python
Python code for fastapi


BookStore API
A simple FastAPI-based project for managing a collection of books. This API allows users to create, retrieve, and view all books.

Overview
This FastAPI application provides endpoints for basic CRUD operations (currently Create and Read) on books. It uses models Book and BookResponse to define request and response data structures.

Features
Get all books

Get a specific book by ID

Add a new book

Requirements
Python 3.10 or higher

FastAPI

Uvicorn

Installation
Clone the repository
git clone https://github.com/modhugu/python.git
cd bookstore-api

Create a virtual environment
python -m venv venv
source venv/bin/activate (For Windows: venv\Scripts\activate)

Install dependencies
pip install fastapi uvicorn

Run the Application
Start the FastAPI server:
uvicorn main:app --reload

Once running, visit the interactive API documentation:

Swagger UI: http://127.0.0.1:8000/docs

ReDoc: http://127.0.0.1:8000/redoc

API Endpoints
Method	Endpoint	Description	Request Body	Response
GET	/books	Retrieve all books	None	List of BookResponse
GET	/books/{book_id}	Retrieve a book by ID	None	BookResponse or None
POST	/books	Create a new book	Book	BookResponse
Example Models
from pydantic import BaseModel

class Book(BaseModel):
title: str
author: str
year: int

class BookResponse(Book):
book_id: int

Example Request
curl -X POST "http://127.0.0.1:8000/books" \
-H "Content-Type: application/json" \
-d '{"title": "1984", "author": "George Orwell", "year": 1949}'

Example Response
{
"book_id": 1,
"title": "1984",
"author": "George Orwell",
"year": 1949
}