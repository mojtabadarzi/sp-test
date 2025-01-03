SP-TEST

A simple React application built with TypeScript to display contacts.

Features
    Contact List: Fetch and display a paginated list of contacts and show contact details.
    Frequent Contacts: Highlight frequently accessed contacts using localStorage.
    Search: Debounced search functionality to filter contacts dynamically.
    Error Handling: Includes utilities for handling errors robustly.
    Tests: Includes a few tests for utilities, hooks, and services to ensure reliability and functionality. 
    (** Important Notes on Search Functionality: On the backend, the first_name and last_name fields are stored with the
        first letter capitalized (e.g., "John" instead of "john").
        As a result, for a search to work correctly, the input must also have the first letter capitalized.
        Example: To search for "Andie" the input must be exactly "John" and not "andie" or "ANDIE"
        Please keep this limitation in mind when testing or reviewing the functionality.)
    (** Enhanced User Experience with useContactsWithCache:
        A custom hook, useContactsWithCache, has been implemented to provide a better user experience.
        What it does:
            When users load more contacts and navigate to a contact's details, they will return to the exact state of the 
            list they last saw, with all previously loaded items still visible.
            This caching mechanism improves usability and ensures users don't lose their progress.
        Default Behavior:
            By default, the useContacts hook is used, which does not cache the list. When users navigate back to the contacts list, they will only see the initial set of items loaded when they first visited the site.
        To test or switch to the cached version, you can replace useContacts with useContactsWithCache in the code.)

Tech Stack
    React: Front-end library.
    TypeScript: For static typing.
    Axios: HTTP client for fetching data.
    Tailwind CSS: Utility-first CSS framework for styling.
    React Router: For routing.
    Jest: Testing framework.
    React Icons: For handle icons

Clone the repository
    git clone
    cd sp-test

Install dependencies:
    npm install

Start the development server:
    npm start
    Open the app in your browser at http://localhost:3000.

Available Scripts
    npm start: Runs the app in development mode.
    npm test: Launches the test runner.
    npm run build: Builds the app for production.
    npm run eject: Ejects the app configuration (use with caution).

Folder Structure
    src/
    ├── components/          # Reusable UI components
    ├── common/              # Shared utilities and helpers
    ├── pages/               # Page components for routing
    ├── hooks/               # Custom React hooks
    ├── services/            # API service functions
    ├── utils/               # Utility functions
    ├── types/               # TypeScript type definitions
    └── constant/            # Constants and configuration

API
    Base URL: http://localhost:1337/passenger
    Endpoints:
        GET /contacts: Fetches a list of contacts.
        POST /contacts: Adds a new contact.

Testing
    Run the tests using Jest:
    npm test