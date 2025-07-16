<h1>Episode 1 : Inception</h1>
  <li>
    The costliest operation in browsers is DOM manipulation and that's why React was created. Since React uses a virtual DOM, it minimizes the number of direct DOM manipulations, making updates faster and more efficient.
  </li>
  <li>
    A CDN (Content Delivery Network) is a network of servers distributed across different locations that helps deliver content (like images, videos, websites, etc.) to users faster and more efficiently.
  </li>
  <li>
    <b>How React CDN links works behind the scenes :</b>
    <ul>
      <li>
        React CDN links (like https://unpkg.com/react@18/...) point to versions of React hosted on a CDN (like unpkg, jsDelivr, etc.).
      </li>
      <li>
        When your browser loads the page:
        <ul>
          <li>
            It sends a request to the CDN for those files.
          </li>
          <li>
            The CDN serves them from the closest server to the user.
          </li>
        </ul>
      </li>
      <li>
        React is now available in the global scope (window.React, window.ReactDOM), and you can use it in <.script> tags like in the example.
      </li>
    </ul>
  </li>
  <li>
    <b>What is task of react-dom :</b>
    <ul>
      <li>
        ReactDOM is a package that converts virtual DOM elements created with React into actual DOM elements that can be rendered in the browser.
      </li>
      <li>
        It has method like <code>ReactDOM.render()</code> which takes a React element and a DOM node, and renders the React element into that DOM node.
      </li>
      <li>
        It uses a method called diffing to differentiate between the old and new virtual DOM trees, and only updates the parts that have changed, making it efficient.
      </li>
    </ul>
  </li>
  <li>
    <b>React.createElement() :</b>
    <ul>
      <li>
        The core function in React that creates a virtual representation of a DOM element (called a React element). React elementt are
        nothing but plain JavaScript objects that describe what the UI should look like.
      </li>
      <li>
        It takes three arguments: the type of element (like 'div', 'span', etc.), an object with properties (like className, id, etc.), and children (which can be other React elements or text).
        If we want to add multiple children, we can pass them as an array.
        Example:
        <pre>
          React.createElement('div', { className: 'my-class' }, 'Hello World');
        </pre>
      </li>
      <li>
        This is used by JSX (the syntax that looks like HTML in React) under the hood to create React elements.
        When you write `<.div className="my-class">Hello World</.div>`, it is transformed into a call to `React.createElement('div', { className: 'my-class' }, 'Hello World')`.
      </li>
      <li>
        It enables React to build the virtual DOM, which allows fast UI updates.
      </li>
    </ul>
  </li>
  <li>
    React replaces the content of root element with the content of the React element.
    <ul>
      <li>
        The root element is the DOM node where React will render its content.
      </li>
    </ul>
  </li>
  <h1>Episode 2 : Igniting our App</h1>
  <li>
    <b>Use of ^ (caret) and ~ (tilde) symbols in package.json : </b>
    <ul>
      <li>
        The caret (^) symbol allow updates that do NOT change the first non-zero number (major version).
        Example: "^18.2.0" allows updates to 18.2.3, 18.3.0, but not 19.0.0. It just blocks major version updates. Allow anything from 18.2.0 up to (but not including) 19.0.0.
      </li>
      <li>
        The tilde (~) symbol allows updates that do NOT change the second non-zero number (minor version).Allow only patch updates, but not minor or major updates.
        Example: "~18.2.0" allows updates to 18.2.3, but not 18.3.0 or 19.0.0. It just blocks minor and major version updates. Allow anything from 18.2.0 up to (but not including) 18.3.0.
    </ul>
  </li>
  <li>
    <b>Difference between dependencies and devDependencies in package.json :</b>
    <ul>
      <li>
        <b>dependencies</b> are packages that your application needs to run in production. (on server or on browser)
        Example: React, ReactDOM, etc.
      </li>
      <li>
        <b>devDependencies</b> are packages that are only needed during development and testing, but not in production.
        Example: Babel, ESLint, etc.
      </li>
      <li>
        Bundlers like Webpack or Parcel will bundle the dependencies and devDependencies together, but when you deploy your app, only the dependencies are needed to run it.
      </li>
      <li>
        When you run `npm install`, it installs both dependencies and devDependencies, but when you run `npm install --production`, it only installs dependencies.
      </li>
      <li>
        What gets deployed to production is the output (typically in a build/ or dist/ folder). Webpack tself is not deployed, but the output of Webpack is.
      </li>
      <li>
        When we push our code to github, a ci/cd pipeline will run the build command, which will use the dependencies and devDependencies to create the output.
      </li>
      <li>
        This creates the build/ or dist/ folder (Webpack bundles everything).
      </li>
      <li>
        Then this build/ folder is deployed to a static file server (e.g., S3, Firebase, NGINX, Apache, etc.).
      </li>
      <li>
        Webpack is installed and used in ci/cd server, but not in actual production server.
      </li>
    </ul>
  </li>
  <h1>Episode 3 : Laying the Foundation</h1>
  <li>
    <b>
      Why we use arrow function in React components and not regular function :
    </b>
    <ul>
      <li>
        Arrow function is shorter and cleaner syntax.
      </li>
      <li>
        Arrow function is not hoisted, so their behavior is more predictable in larger components where the order of definition matters.
      </li>
    </ul>
  </li>