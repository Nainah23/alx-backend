# 0x02-i18n

This project involves setting up a Flask web application with internationalization support using the Flask-Babel extension. The project demonstrates how to create a multilingual web application that can adapt to different languages and time zones based on user preferences and request parameters.

## Tasks

### 0. Basic Flask app
Create a basic Flask app with a single route that renders a template displaying a welcome message.

- **File**: `0-app.py`, `templates/0-index.html`
- **Route**: `/`
- **Template**: Displays "Welcome to Holberton" as the page title and "Hello world" as the header.

### 1. Basic Babel setup
Install Flask-Babel and configure the Flask app to support English and French languages.

- **File**: `1-app.py`, `templates/1-index.html`
- **Dependencies**: `flask_babel==2.0.0`
- **Configuration**: Default locale is "en" and default timezone is "UTC".

### 2. Get locale from request
Implement a function to determine the best language match from the request's accepted languages.

- **File**: `2-app.py`, `templates/2-index.html`
- **Function**: `get_locale` with `babel.localeselector` decorator.

### 3. Parametrize templates
Use the `_` or `gettext` function to parametrize the templates for translation. Create translation files and compile them.

- **File**: `3-app.py`, `babel.cfg`, `templates/3-index.html`, `translations/en/LC_MESSAGES/messages.po`, `translations/fr/LC_MESSAGES/messages.po`, `translations/en/LC_MESSAGES/messages.mo`, `translations/fr/LC_MESSAGES/messages.mo`
- **Translations**: Use the message IDs `home_title` and `home_header`.

### 4. Force locale with URL parameter
Modify the `get_locale` function to allow forcing a locale via URL parameters.

- **File**: `4-app.py`, `templates/4-index.html`
- **URL Parameter**: `locale=[fr|en]`

### 5. Mock logging in
Simulate user login by passing a `login_as` URL parameter. Display a welcome message if a user is logged in.

- **File**: `5-app.py`, `templates/5-index.html`
- **User Data**: Mock user table with predefined users.
- **Function**: `get_user`, `before_request` decorator to set user in `flask.g.user`.

### 6. Use user locale
Update the `get_locale` function to use the user's preferred locale if available.

- **File**: `6-app.py`, `templates/6-index.html`
- **Locale Priority**:
  1. Locale from URL parameters
  2. Locale from user settings
  3. Locale from request header
  4. Default locale

### 7. Infer appropriate time zone
Implement a function to infer the appropriate time zone based on URL parameters, user settings, or default to UTC.

- **File**: `7-app.py`, `templates/7-index.html`
- **Function**: `get_timezone` with `babel.timezoneselector` decorator.
- **Validation**: Validate time zones using `pytz.timezone`.

### 8. Display the current time (Advanced)
Display the current time on the home page based on the inferred time zone in the appropriate language.

- **File**: `app.py`, `templates/index.html`, `translations/en/LC_MESSAGES/messages.po`, `translations/fr/LC_MESSAGES/messages.po`
- **Translations**: Use the message ID `current_time_is`.

## Repository Structure
```
alx-backend/
├── 0x02-i18n/
│   ├── 0-app.py
│   ├── 1-app.py
│   ├── 2-app.py
│   ├── 3-app.py
│   ├── 4-app.py
│   ├── 5-app.py
│   ├── 6-app.py
│   ├── 7-app.py
│   ├── app.py
│   ├── babel.cfg
│   ├── templates/
│   │   ├── 0-index.html
│   │   ├── 1-index.html
│   │   ├── 2-index.html
│   │   ├── 3-index.html
│   │   ├── 4-index.html
│   │   ├── 5-index.html
│   │   ├── 6-index.html
│   │   ├── 7-index.html
│   │   ├── index.html
│   ├── translations/
│   │   ├── en/
│   │   │   └── LC_MESSAGES/
│   │   │       ├── messages.po
│   │   │       └── messages.mo
│   │   ├── fr/
│   │   │   └── LC_MESSAGES/
│   │   │       ├── messages.po
│   │   │       └── messages.mo
```

## How to Run
1. Install the required dependencies:
   ```sh
   pip3 install flask flask_babel==2.0.0 pytz
   ```

2. Run the Flask application:
   ```sh
   flask run
   ```

3. Access the application in your web browser:
   ```
   http://127.0.0.1:5000/
   ```

4. Test different locales by adding the `locale` URL parameter:
   ```
   http://127.0.0.1:5000/?locale=fr
   http://127.0.0.1:5000/?locale=en
   ```

5. Mock login by adding the `login_as` URL parameter:
   ```
   http://127.0.0.1:5000/?login_as=1
   ```
