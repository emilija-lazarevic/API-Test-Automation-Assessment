# Test scenarios

This document outlines test scenarios for user and admin roles.

## Table of Contents
  - [User role scenarios](#user-role-scenarios)
  - [Admin role scenarios](#admin-role-scenarios)
  - [Excluded scenarios](#excluded-scenarios)
    - [Excluded User role scenarios](#excluded-user-role-scenarios)
    - [Excluded Admin role scenarios](#excluded-admin-role-scenarios)


## User role scenarios

```gherkin
Feature: User registration


Scenario: Successful registration
Given the user enters a proper email address
And the user enters a proper password
Then the API returns status code 200
And the API assigns a user ID to the account
And the API returns a session token


Scenario: Unsuccessful registration with a bad email format
Given the user enters an email address that is in a wrong format
And the user enters a password
Then the API returns status code 400
And the API returns an error message


Scenario: Unsuccessful registration without an email
Given the user leaves the email field empty
And the user enters a password
Then the API returns status code 400
And the API returns 'Missing email or username' error message


Scenario: Unsuccessful registration without an password
Given the user enters a proper email address
And the user leaves the password field empty
Then the API returns status code 400
And the API returns 'Missing password' error


Scenario: Unsuccessful registration with a wrong HTTP method
Given the user tries to send a registration request through a PUT/PATCH method
Then the API returns status code 404

```

```gherkin
Feature: User Login


Scenario: Successful login
Given the user enters a correct username
And the user enters the correct password
Then the API returns status code 200 and a session token


Scenario: Unsuccessful login with a bad username
Given the user enters a non-existing username
Then the API returns status code 400 
And the API returns 'User not found' error message


Scenario: Unsuccessful login without a username
Given the user leaves the username field empty
And the user enters a password
Then the API returns status code 400
And the API returns 'Missing email or username' error message 


Scenario: Unsuccessful login without a password
Given the user enters an existing username
And the user leaves the password field empty
Then the API returns status code 400
And the API returns 'Missing password' error message


Scenario: Unsuccessful login with a wrong HTTP method
Given the user tries to send a login request through a PUT/PATCH method
Then the API returns status code 404

```

```gherkin
Feature: User logout


Scenario: Successful logout
Given logged in user triggers the logout endpoint
Then the API returns status code 200

```



## Admin role scenarios

```gherkin
Feature: Update user


Scenario: Successful user update through the PATCH method
Given that the admin user is logged in
And the admin sends data to update for a specific user ID
Then the API returns status code 200
And the API returns updated properties
And the API returns a timestamp of the update


Scenario: Successful user update through the PUT method
Given that the admin user is logged in
And the admin sends data to update for a specific user ID
Then the API returns status code 200
And the API returns updated properties
And the API returns a timestamp of the update

```

```gherkin
Feature: Delete user


Scenario: Successful deletion of a user
Given that the admin user is logged in
And the admin sends a DELETE request for a user ID
Then the API returns status code 204

```

# Excluded scenarios

These are scenarios that are excluded simply because of the limitation of the mocked API and they would have replaced some of the automated scenarios.

## Excluded User role scenarios

```gherkin
Feature: User registration


Scenario: Unsuccessful registration with an already registered email address
Given that the user enters an already registered email address
Then the API returns status code 400
And the API returns an error message

```

```gherkin
Feature: User login


Scenario: Unsuccessful login with an incorrect password
Given that the user enters a registered username
And the user enters an incorrect password for that username
Then the API returns status code 400
And the API returns an error message

```

```gherkin
Feature: User logout


Scenario: Unsuccessful logout when the user is not logged in
Given that the user is not logged in
And thee user sends a logout request
Then the API returns status code 400
And the API returns an error message

```



## Excluded Admin role scenarios

```gherkin
Feature: Update user


Scenario: Unsuccessful update of a non-existing user
Given that the admin user is logged in
And the user sends an update request for a non-existing user ID
Then the API returns status code 400
And the API returns an error message



Scenario: Unsuccessful update through a non-admin user
Given that the user that is logged in is not an admin
And the user sends an update request for a user ID
Then the API returns status code 403
And the API returns an error message

```

```gherkin
Feature: Delete user


Scenario: Unsuccessful deletion of a non-existing user
Given that the admin user is logged in
And the admin sends a DELETE request for a non-existing user
Then the API returns status code 400
And the API returns an error message



Scenario: Unsuccessful deletion through a non-admin user
Given that the user that is logged in is not an admin
And the user sends a DELETE request for a user ID
Then the API returns status code 403
And the API returns an error message
```

