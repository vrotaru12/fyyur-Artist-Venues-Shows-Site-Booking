Fyyur
-----

### Introduction

Fyyur is a musical venue and artist booking site that facilitates the discovery and bookings of shows between local performing artists and venues. This site lets you list new artists and venues, discover them, and list shows with artists as a venue owner.

### Tech Stack

Our tech stack will include:

* **SQLAlchemy ORM** to be our ORM library of choice
* **PostgreSQL** as our database of choice
* **Python3** and **Flask** as our server language and server framework
* **Flask-Migrate** for creating and running schema migrations
* **HTML**, **CSS**, and **Javascript** with [Bootstrap 3](https://getbootstrap.com/docs/3.4/customize/) for our website's frontend

### Main Files: Project Structure

  ```sh
  ├── README.md
  ├── app.py *** the main driver of the app. Includes your SQLAlchemy models.
                    "python app.py" to run after installing dependences
  ├── config.py *** Database URLs, CSRF generation, etc
  ├── error.log
  ├── forms.py *** Your forms
  ├── requirements.txt *** The dependencies we need to install with "pip3 install -r requirements.txt"
  ├── static
  │   ├── css 
  │   ├── font
  │   ├── ico
  │   ├── img
  │   └── js
  └── templates
      ├── errors
      ├── forms
      ├── layouts
      └── pages
  ```

Overall:
* Models are located in the `MODELS` section of `app.py`.
* Controllers are also located in `app.py`.
* The web frontend is located in `templates/`, which builds static assets deployed to the web server at `static/`.
* Web forms for creating data are located in `form.py`


Highlight folders:
* `templates/pages` -- (Already complete.) Defines the pages that are rendered to the site. These templates render views based on data passed into the template’s view, in the controllers defined in `app.py`. These pages successfully represent the data to the user, and are already defined for you.
* `templates/layouts` -- (Already complete.) Defines the layout that a page can be contained in to define footer and header code for a given page.
* `templates/forms` -- (Already complete.) Defines the forms used to create new artists, shows, and venues.
* `app.py` -- (Missing functionality.) Defines routes that match the user’s URL, and controllers which handle data and renders views to the user. This is the main file you will be working on to connect to and manipulate the database and render views with data to the user, based on the URL.
* Models in `app.py` -- (Missing functionality.) Defines the data models that set up the database tables.
* `config.py` -- (Missing functionality.) Stores configuration variables and instructions, separate from the main application code. This is where you will need to connect to the database.


Steps followed
-----
1. Built and run local development following the Development Setup steps below.
2. Filled in the missing functionality in this application: this application initialy pulled in fake data, and needed a real connection to database and talk to a real backend.
3. The code contans `TODO` section throughout the codebase. So the steps taken were the following:
  1. Connect to a database in `config.py`. A local database was used.
  2. Using SQLAlchemy, set up normalized models for the objects in the Models section of `app.py`. Checked out the sample pages provided at /artists/1, /venues/1, and /shows/1 for examples of the data needed to model, using all of the learned best practices in database schema design. Implement missing model properties and relationships using database migrations via Flask-Migrate.
  3. Implemented form submissions for creating new Venues, Artists, and Shows. There should be proper constraints, powering the `/create` endpoints that serve the create form templates, to avoid duplicate or nonsensical form submissions. Submitting a form should create proper new records in the database.
  4. Implemented the controllers for listing venues, artists, and shows. The mock data structure needs to be kept.
  5. Implemented search, powering the `/search` endpoints that serve the application's search functionalities.
  6. Served venue and artist detail pages, powering the `<venue|artist>/<id>` endpoints that power the detail pages.

### Development Setup

First, [install Flask](http://flask.pocoo.org/docs/1.0/installation/#install-flask) if you haven't already.

  ```
  $ cd ~
  $ pip install Flask
  ```

To start and run the local development server,

1. Initialize and activate a virtualenv:
  ```
  $ cd YOUR_PROJECT_DIRECTORY_PATH/
  $ virtualenv --no-site-packages env
  $ source env/bin/activate
  ```

2. Install the dependencies:
  ```
  $ pip install -r requirements.txt
  ```

3. Run the development server:
  ```
  $ export FLASK_APP=myapp
  $ export FLASK_ENV=development # enables debug mode
  $ py app.py
  ```

4. Navigate to Home page [http://localhost:5000](http://localhost:5000)

## Authors
Victoria Rotaru authored app.py, config  suite (config.py), forms.py, and this README. Also, added additional Javascript code in forms (html templates).
All other project files, including frontend, were created by Udacity as a project template for the Full Stack Web Developer Nanodegree.
