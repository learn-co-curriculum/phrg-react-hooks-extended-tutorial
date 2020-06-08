# Extending Your CRUD Application

Now that we have a working CRUD application using React hooks, let's have some fun with it. Navigate back to your project and create a custom branch before starting.

## Refactor

First, let's refactor some of the code in our `AddUserForm.js` and `EditUserForm.js`. Did you notice that the `onSubmit` prop in our `<form>`s are passed anonymous functions? This may look okay for short callbacks, like the one-liner for the `onClick` prop on some of the app's buttons. But it is better to separate more complex logic out of React's Virtual DOM and place it higher in the function definition.

Take the `handleInputChange` function as an example. Moving the logic of this callback into the body of the `AddUserForm` `const` not only `DRY`ed the application, but it made the Virtual DOM easier to read.

In Nitro, ESLint prevents anonymous functions from getting passed to props in our React code. So let's not do that in this project either!

Replace the `<form ...` in `AddUserForm` and `EditUserForm` with `<form onSubmit={handleSubmit}>` and move its logic into a `handleSubmit` `const`. Use `handleInputChange` as an example.

*Commit the work to your custom branch.*

#### BONUS

Refactor all the anonymous functions passed to props out of the project.

## New User Field

Let's add a new field to our user records. Every user will now have a `name`, a `username`, and a `spiritAnimal`. Here are some things to check as you make this addition:

- Initial user records
- Initial form state
- The user table display
- The new and edit forms

*Commit the work to your custom branch.*

## Delete All Users

Let's add a feature that allows the users of our application to delete ALL the user's in the application. To accomplish this, add a button below the `UserTable` in the `App.js` like so:

```js
<button
    className="button muted-button"
    onClick={deleteUsers}>
  {'Delete All Users'}
</button>
```

Then write a `deleteUsers` function to handle removing all of the user records.

When you are done, your Application should look something like this:

![Spirit Animals](https://raw.githubusercontent.com/powerhome/phrg-react-hooks-extended-tutorial/master/spiritAnimals.png?raw=true "Spirit Animals")

*Commit the work to your custom branch.*

## Merge your work

Navigate to your repo on Github, open up a Pull Request for your custom branch, and merge it to `master`.

## BONUS

Have an idea for another feature? Go for it!

Before you start, create another custom branch and commit often.

Once you finish, open up another Pull Request and show off your changes to the class.

