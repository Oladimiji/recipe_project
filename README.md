Recipe Management API
This is a backend-focused Recipe Management API built with Django and Django REST Framework. The API allows users to manage recipes, including creating, updating, and deleting them. 
It features robust user authentication, advanced search capabilities, and a system for ratings, reviews, and favorites.
Features
 * User Authentication: Secure user registration and authentication using Django's built-in system.
 * Recipe Management: Full CRUD operations for recipes. Each recipe includes details like title, description, ingredients, cooking time, and servings.
 * Personalized Content: Users can only create, edit, or delete their own recipes, ensuring data integrity and security.
 * Advanced Search & Filtering:
   * Search: Find recipes by Title, Category, or Ingredients.
   * Filtering: Refine searches by Cooking Time, Preparation Time, or Servings.
 * Pagination & Sorting: Efficiently navigate through large recipe lists with paginated results and sort them by time or servings.
 * Recipe Ratings & Reviews: Users can rate recipes (1-5 stars) and leave reviews.
 * Favorite Recipes: A feature that allows authenticated users to save and view their favorite recipes.
 * Admin Panel: A fully functional Django Admin panel to manage users, recipes, and other data models.
Technologies Used
 * Python: The core programming language.
 * Django: The high-level web framework used for rapid development.
 * Django REST Framework (DRF): A powerful toolkit for building the API endpoints.
 * Django Filters: Used for advanced filtering capabilities.
 * PostgreSQL: (Recommended for deployment) A powerful, open-source relational database.
Installation and Setup
Follow these steps to get a local copy of the project up and running on your machine.
Prerequisites
 * Python 3.8 or higher
 * pip (Python package installer)
Steps
 * Clone the Repository:
   git clone https://github.com/your-username/recipe_project.git
cd recipe_project

 * Create and Activate a Virtual Environment:
   This practice isolates your project dependencies from other Python projects.
   python -m venv venv
source venv/bin/activate  # On Windows, use venv\Scripts\activate

 * Install Dependencies:
   The requirements.txt file lists all the necessary libraries.
   pip install -r requirements.txt

 * Database Migrations:
   Apply the database schema changes to your local database.
   python manage.py makemigrations
python manage.py migrate

 * Create a Superuser:
   This will give you access to the Django Admin panel.
   python manage.py createsuperuser

 * Run the Development Server:
   python manage.py runserver

   The API will now be accessible at http://127.0.0.1:8000/.
API Endpoints
The API is built following RESTful principles and is accessible at the /api/ prefix.
| Endpoint | HTTP Method | Description |
|---|---|---|
| /api/register/ | POST | Creates a new user account. |
| /api/recipes/ | GET | Lists all recipes. Supports search, filtering, and pagination. |
| /api/recipes/ | POST | Creates a new recipe (requires authentication). |
| /api/recipes/<id>/ | GET | Retrieves a specific recipe by ID. |
| /api/recipes/<id>/ | PUT, PATCH | Updates a recipe (requires authentication; only by owner). |
| /api/recipes/<id>/ | DELETE | Deletes a recipe (requires authentication; only by owner). |
| /api/categories/ | GET | Lists all recipe categories. |
| /api/ingredients/ | GET | Lists all ingredients. |
| /api/reviews/ | GET, POST | Lists all reviews or creates a new one (requires authentication). |
| /api/reviews/<id>/ | GET, PUT, DELETE | Manages a specific review. |
| /api/favorites/ | GET, POST | Lists the user's favorites or adds a new one (requires authentication). |
| /api/favorites/<id>/ | DELETE | Removes a favorite. |
Deployment
The project is configured for deployment on platforms like Heroku or PythonAnywhere.
Dependencies: gunicorn and whitenoise have been added to the requirements.txt file for a production environment.
