import React, { useState } from 'react';
import { BrowserRouter as Router, Route, Link } from 'react-router-dom';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
      <button onClick={() => setCount(count - 1)}>Decrease</button>
    </div>
  );
}

function Greeting() {
  return <h2>Hello, Welcome to My SPA!</h2>;
}

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/counter">Counter</Link>
            </li>
          </ul>
        </nav>

        <Route path="/" exact component={Greeting} />
        <Route path="/counter" component={Counter} />
      </div>
    </Router>
  );
}

export default App;
