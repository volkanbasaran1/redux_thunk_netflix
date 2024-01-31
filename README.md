![ekran](https://github.com/volkanbasaran1/redux_thunk_netflix/assets/76842256/63bb3d82-afec-41cc-9bc5-d27c40f2ea17)
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
        }
        h1 {
            color: #e50914;
        }
        h2 {
            color: #b31217;
        }
        p {
            color: #fff;
        }
        code {
            background-color: #eee;
            padding: 2px 4px;
            border-radius: 4px;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            margin-bottom: 10px;
        }
        pre {
            background-color: #333;
            color: #fff;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }
        a {
            color: #007bff;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>Netflix Clone with Redux Thunk</h1>
    <p>This project is a clone of Netflix's user interface, developed using React and Redux Thunk.</p>
    <h2>Getting Started</h2>
    <ol>
        <li><strong>Clone the Repository:</strong></li>
        <pre><code>git clone https://github.com/yourusername/netflix-clone.git
cd netflix-clone</code></pre>
        <li><strong>Install Required Packages:</strong></li>
        <pre><code>npm install</code></pre>
        <li><strong>Run the Application:</strong></li>
        <pre><code>npm start</code></pre>
        <p>The application will run at <a href="http://localhost:3000">http://localhost:3000</a>.</p>
    </ol>
    <h2>Technologies Used</h2>
    <ul>
        <li>React</li>
        <li>Redux and Redux Thunk</li>
        <li>React Router</li>
        <li>Axios (for API communication)</li>
    </ul>
    <h2>Project Structure</h2>
    <pre><code>src
|-- components
|-- redux
|   |-- actions
|   |-- reducers
|   |-- thunks
|   |-- store.js
|-- services
|-- App.js</code></pre>
    <h2>Redux Thunk Usage</h2>
    <p>Redux Thunk is used for managing asynchronous operations. In this project, it is used to fetch data from an API and add it to the Redux store.</p>
    <p>Example of a Thunk action:</p>
    <pre><code>// src/redux/thunks/movieThunks.js
import { getPopularMoviesSuccess, getPopularMoviesFailure } from '../actions/movieActions';
import axios from 'axios';
export const getPopularMovies = () => {
  return async (dispatch) => {
    try {
      const response = await axios.get('/api/movies/popular');
      dispatch(getPopularMoviesSuccess(response.data));
    } catch (error) {
      dispatch(getPopularMoviesFailure(error.message));
    }
  };
};</code></pre>
    <p>In this example, a Thunk action is used to get popular movies from an API and dispatch success or failure actions based on the API response.</p>

</body>

</html>
