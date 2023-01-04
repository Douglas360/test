# React Hooks Movie Management Application

React movies application provides a simple list of movies.

----

## Main features

Your task is to complete a simple movie management application by adding 4 main features:
- Listing all the movies
- Creating a new movie by filling a form
- Deleting an existing movie
- Rating a movie using stars 1-5

Make sure that:
- all the tests pass
- you stick to the names of the props of the original components (don't refactor them), so that the automatic tests don't break

## Application

- Each *movie* contains `id`, `title`, `subtitle`, `description`, `imageUrl` and `ratings` fields. See typescript types in the `types.ts` file
    - `data/movies.json` and `data/testdata.ts` files provide movies for the app and the tests, respectively
- `api/movies.ts` file includes function which retrieves the movies data
- `movies/ratings.ts` file includes functions related to the Movie model (average rate)
- `movies/useMoviesReducer.tsx` file includes a stub of a react hook which implements state management, used by the `MovieProvider`
- `shared/components` folder contains helper "view" components, e.g. for star rating and form inputs

## Requirements

- Implement `MovieCard` component that will display data and actions of a single movie it gets through a prop
  - `imageUrl`, `title`, `subtitle`, `description`
  - Add delete option for a movie, which should call a handler and dispatch an appropriate action
  - Display stars that are clickable through `StarRating` component
  - Display an average rating
- In `movies/useMoviesReducer.tsx` file, the `useMoviesReducer` custom hook (built on top of `useReducer` and used in `MovieProvider` to pass down its state via context) should allow to dispatch following actions:
  - `fetch` - provide initial data with `api/movies`
  - `add` - add a new valid movie, thanks to filling a form
  - `delete` - delete a certain movie by clicking a button
  - `rate` - rate a movie (which aggregates all the rates)
- Finish `MovieList` component which displays a list of movies as `MovieCard`s
  - `Card` at the end should contain an `AddMovieButton` initially, or display `AddMovieForm` once clicked
  - Each of the actions inside `AddMovieForm` (adding a movie or canceling the form) should lead back to the `AddMovieButton`
- Finish `AddMovieButton` component to display `Add movie` label and to call appropriate handler (that switches to form)
- Implement `AddMovieForm` component that should show 4 text input fields: `url` (of the movie image), `title`, `subtitle` and `description`. When all the fields are filled and the form is submitted, a new movie should be added and displayed

## Setup

Follow these steps for correct application setup:

1. `npm install` – install dependencies
2. `npm test` – run all tests (should fail unless you fix the app)
3. `npm run test:watch` - run all tests in _watch mode_ (optionally, you can use it locally if you prefer)
4. `npm start` – serve the app at [http://localhost:3000/](http://localhost:3000/) (it automatically opens the app in your default browser)

## Good Luck!
