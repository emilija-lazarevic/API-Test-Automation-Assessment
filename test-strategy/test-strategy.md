# Test strategy for reqres.in API

## Table of Contents
  - [Introduction](#introduction)
  - [Types of tests to be executed](#types-of-tests-to-be-executed)
    - [Functional testing](#functional-testing)
    - [Non-functional testing](#non-functional-testing)
  - [Excluded tests](#excluded-tests)


# Introduction

This test strategy document is written under the assumption the API will be used in a business forum online, with a large number of registered users.

Users can register a new account using a valid email address and a strong password (it should be minimum 8 characters long, contain at least one upper case letter, a number and a special character).

Admins of the forum can update the user info if it is needed and they can ban (delete) users if they express inappropriate behaviour.



# Types of tests to be executed

In this section it is described what types of tests will be executed and the reasoning behind choosing them.

- #### **Functional testing:**

  - **Unit tests** : It is important for developers to write unit tests as components are developed, or even develop them before any code is written (TDD). This evaluates that the components are working as intended from the early stages development.
  - **Integration tests**: When multiple components are being developed, it is important to test that they actually work together and add up to create a functional application.
  - **API tests**: This will evaluate the individual endpoints work in real life scenarios.
  - **E2E API tests**: This will evaluate the whole application flow works in real life scenarios.
  
- #### **Non-functional testing**:

  - **Requirement testing**: Before starting with the development of the software, we need to ensure that the requirements are complete, clear and consistent.
  - **Performance testing**: The forum could potentially have a large amount of users trying to access it at the same time. We should ensure the application is able to respond fast in these situations.



# Excluded tests

- **Security testing**: While I do think we need to perform some basic security testing (ensure users have to use strong passwords during registration, 2FA is in place, that there are lockouts after X number of failed login attempts, the login session expires after X amount of time), I believe it is not needed to perform rigorous security testing for a public forum application.
 
