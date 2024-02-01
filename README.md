# Library Management System

## Project Overview
This project is a simple library management system developed using Django and Django REST framework. Check the "MASTER BRANCH"

## Setup Instructions

### Prerequisites
- Python 3.x
- Django 3.x
## Database
This project uses MySQL as the relational database management system. Make sure you have MySQL installed on your system.

### Database Configuration
1. Open the `library_project/settings.py` file.
2. Locate the `DATABASES` setting.
3. Update the `DATABASES` setting with your MySQL database configuration, including `NAME`, `USER`, `PASSWORD`, etc.

Example:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'library_db',
        'USER': 'sulav',
        'PASSWORD': 'sulav',
        'HOST': 'localhost',
        'PORT': '3306',
    }   
}
### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/codenextdoor/library-management-system/
   cd library-management-system

API Documentation
1. User APIs
Create a New User

Endpoint: POST /api/create_user/
Required Data:
{
  "Name": "John Doe",
  "Email": "john@example.com",
  "MembershipDate": "2024-01-31"
}
Response (Success):

{
  "UserID": 1,
  "Name": "John Doe",
  "Email": "john@example.com",
  "MembershipDate": "2024-01-31"
}
List All Users

Endpoint: GET /api/list_all_users/
Response (Example):

[
  {
    "UserID": 1,
    "Name": "John Doe",
    "Email": "john@example.com",
    "MembershipDate": "2024-01-31"
  },
  ...
]
Get User by ID

Endpoint: GET /api/get_user_by_id/<user_id>/
Response (Example):

{
  "UserID": 1,
  "Name": "John Doe",
  "Email": "john@example.com",
  "MembershipDate": "2024-01-31"
}
2. Book APIs
Add a New Book

Endpoint: POST /api/add_new_book/
Required Data:

{
  "Title": "The Great Gatsby",
  "ISBN": "9780140283334",
  "PublishedDate": "2023-12-01",
  "Genre": "Fiction"
}
Response (Success):

{
  "BookID": 1,
  "Title": "The Great Gatsby",
  "ISBN": "9780140283334",
  "PublishedDate": "2023-12-01",
  "Genre": "Fiction"
}
List All Books

Endpoint: GET /api/list_all_books/
Response (Example):

[
  {
    "BookID": 1,
    "Title": "The Great Gatsby",
    "ISBN": "9780140283334",
    "PublishedDate": "2023-12-01",
    "Genre": "Fiction"
  },
  ...
]
Get Book by ID

Endpoint: GET /api/get_book_by_id/<book_id>/
Response (Example):

{
  "BookID": 1,
  "Title": "The Great Gatsby",
  "ISBN": "9780140283334",
  "PublishedDate": "2023-12-01",
  "Genre": "Fiction"
}
Assign/Update Book Details

Endpoint: PUT /api/get_or_update_book/<book_id>/
Required Data:

{
  "Pages": 300,
  "Publisher": "Penguin Books",
  "Language": "English"
}
Response (Success):

{
  "BookID": 1,
  "Title": "The Great Gatsby",
  "ISBN": "9780140283334",
  "PublishedDate": "2023-12-01",
  "Genre": "Fiction",
  "Pages": 300,
  "Publisher": "Penguin Books",
  "Language": "English"
}
3. BorrowedBooks APIs
Borrow a Book

Endpoint: POST /api/borrow_book/
Required Data:

{
  "UserID": 1,
  "BookID": 1,
  "BorrowDate": "2024-02-01"
}
Response (Success):

{
  "BorrowedBookID": 1,
  "UserID": 1,
  "BookID": 1,
  "BorrowDate": "2024-02-01"
}
Return a Book

Endpoint: PUT /api/return_book/<borrowed_book_id>/
Required Data:

{
  "ReturnDate": "2024-02-15"
}
Response (Success):

{
  "message": "Book returned successfully"
}
List All Borrowed Books

Endpoint: GET /api/list_all_borrowed_books/
Response (Example):

[
  {
    "BorrowedBookID": 1,
    "UserID": 1,
    "BookID": 1,
    "BorrowDate": "2024-02-01",
    "ReturnDate": null
  },
  ...
]

Additional Notes
Make sure to replace placeholder values (e.g., <user_id>, <book_id>, <borrowed_book_id>) with actual values.
The date format used is YYYY-MM-DD.
