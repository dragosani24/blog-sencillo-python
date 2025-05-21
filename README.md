# Django Blog Project

A simple blog application built with the Django web framework. It allows users to create, publish, and view blog posts.

## Features

- User authentication (via Django's built-in auth) for authors.
- Post creation, editing, and deletion (likely managed via the Django admin interface).
- Publication workflow (posts have a `published_date` and a `publish` method).
- Display of a list of posts.
- Display of individual post details.

## Requirements

- Django ~= 5.1.2

## Setup and Installation

Follow these steps to get the project running locally:

1.  **Clone the repository:**
    Replace `<repository-url>` with the actual URL of the repository and `<repository-directory>` with the name of the project directory.
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv myvenv
    source myvenv/bin/activate  # On Windows use `myvenv\Scripts\activate`
    ```

3.  **Install dependencies:**
    Make sure you have a `requirements.txt` file in your project root.
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run database migrations:**
    This will apply the database schema changes.
    ```bash
    python manage.py migrate
    ```

5.  **Create a superuser (for admin access):**
    You will be prompted to create a username, email, and password.
    ```bash
    python manage.py createsuperuser
    ```

6.  **Run the development server:**
    The application will typically be available at `http://127.0.0.1:8000/`.
    ```bash
    python manage.py runserver
    ```

## Usage

Here's how to interact with the running application:

1.  **Accessing the Blog:**
    *   Once the development server is running (after `python manage.py runserver`), the main blog page, which lists published posts, can typically be accessed at `http://127.0.0.1:8000/`.

2.  **Admin Panel:**
    *   The Django admin interface is available at `http://127.0.0.1:8000/admin/`.
    *   Log in using the superuser credentials you created during the setup process (`python manage.py createsuperuser`).

3.  **Managing Posts:**
    *   **Creation, Editing, Deletion:** Through the admin panel, you can create new blog posts, modify existing ones, and remove posts. Look for the "Posts" section (or a similar name) after logging into the admin interface.
    *   **Publishing:** Posts typically have a title and text content. To make a post visible on the main blog, it needs to be published. This usually involves setting a `published_date` for the post. The exact mechanism for publishing (e.g., a specific "publish" action in the admin or simply setting the date and saving) might vary based on the project's specific admin configuration. Once published, the post will appear on the main blog page.

## Configuration Notes

This section details important configuration settings found in `mysite/settings.py`.

1.  **Internationalization:**
    *   The project is configured for Spanish: `LANGUAGE_CODE = 'es-es'`.
    *   The timezone is set to: `TIME_ZONE = 'America/Mazatlan'`.

2.  **Development Settings:**
    *   **DEBUG Mode:** `DEBUG = True` is currently active. This is suitable for development but **must be set to `False` in a production environment** for security reasons.
    *   **Allowed Hosts:** `ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']`. This list defines which host/domain names the Django site can serve. You may need to add your specific domain or IP address here when deploying to a new environment.
