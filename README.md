# CS 85 Laravel 12 Starter Kit app w/ authentication by Fortify
CS 85, Module 10, Assignment 10A, by Gregory Hagen, 7/25/26

GitHub repo: https://github.com/Greg01001000/module10a-auth

## Short-answer questions
### In your own words, what is the difference between authentication and authorization?
Authentication is determining who a user is. The first time a user registers with an app, authentication is creating a stored identity for that user, usually using an email address, and sometimes additional identifying info. After that, authentication is confirming that the user matches that stored identity, usually by having the user enter their password to log in. In contrast, authorization is confirming that the logged-in user is allowed to do a particular action, e.g., delete a blog post.
### Why are passwords hashed instead of stored as plain text?
Storing hashed (not plain text) passwords means that even if someone gets the stored list of hashes, they cannot use those to log in. To log in, a user must submit the actual password, and the app converts that to its hash and compares that to the stored hash. Submitting the hash instead of the actual password would result in a different (incorrect) hash being generated, which would not match the stored hash. And no algorithm can convert hashes in reverse to their passwords.
### Which package registers the /login and /register routes, and which artisan command lets you see them?
Fortify registers those routes. The CLI command `php artisan route:list` shows all the routes.
### What does the auth middleware do, and what happens when a logged-out user hits a page protected by it?
The auth middleware guards access to protected web pages. When a logged-out user tries to load a protected page, the user is redirected to the login page, and after successfully logging in (authenticating), they are redirected to the protected page.