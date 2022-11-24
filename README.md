# Putting it All Together: Client-Server Communication

## Learning Goals

- Understand how to communicate between client and server using fetch, and how
  the server will process the request based on the URL, HTTP verb, and request
  body
- Debug common problems that occur as part of the request-response cycle

## Introduction

Just like the last lesson, we've got code for a React frontend and Rails API
backend set up. This time though, it's up to you to use your debugging skills to
find and fix the errors!

To get the backend set up, run:

```console
$ bundle install
$ rails db:migrate db:seed
$ rails s
```

Then, in a new terminal, run the frontend:

```console
$ npm install --prefix client
$ npm start --prefix client
```

Confirm both applications are up and running by visiting
[`localhost:4000`](http://localhost:4000) and viewing the list of toys in your
React application.

## Deliverables

In this application, we have the following features:

- Display a list of all the toys
- Add a new toy when the toy form is submitted
- Update the number of likes for a toy
- Donate a toy to Goodwill (and delete it from our database)

The code is in place for all these features on our frontend, but there are some
problems with our API! We're able to display all the toys, but the other three
features are broken.

Use your debugging tools to find and fix these issues.

There are no tests for this lesson, so you'll need to do your debugging in the
browser and using the Rails server logs and `byebug`.

**Note**: You shouldn't need to modify any of the React code to get the
application working. You should only need to change the code for the Rails API.

As you work on debugging these issues, use the space in this README file to take
notes about your debugging process. Being a strong debugger is all about
developing a process, and it's helpful to document your steps as part of
developing your own process.

## Your Notes Here

- Add a new toy when the toy form is submitted

  - How I debugged:
  1. Opened the network debug tab on the frontend and previewes the error i.e 500 Internal Server Error.
  2. Opened my Rails server log and looked for the last request that came through i.e NameError (uninitialized constant ToysController::Toys).
  3. The error was a typo i.e Toys instead of Toy.

- Update the number of likes for a toy

  - How I debugged:
  1. Checked my browsers console and the error was Unexpected end of JSON input.
  2. I checked my fetch request first.
  3. I then checked the controller action and made sure to render JSON.

- Donate a toy to Goodwill (and delete it from our database)

  - How I debugged:
  1. I checked the network tab on the frontend.
  2. I then checked the rails server logs in the backenf for the last request that came through.
  3. I then added a new route to handle the DELETE request and the path for the request. 
