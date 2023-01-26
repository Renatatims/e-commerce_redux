# e-commerce_redux
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

  ## Description
  This project consists of a code refactor of an e-commerce platform that uses React's Context API to Redux.

  ![preview](/client/src/assets/screenshots/Capture1.PNG "Preview Application")

  ## Table of Contents
  - [Installation](#installation)
  - [Usage](#usage)
  - [Features](#features)
  - [License](#license)
  - [Contributing](#contributing)
  - [Tests](#tests)
  - [Questions](#questions)
  - [Credits](#credits)
  
  ## Installation
  ```npm i``` to install all the packages .

  ## Usage
  E-commerce platform that uses Redux to manage global state instead of the Context API.

  ## Features
  User can browse products per category, add and remove from Cart, and adjust item's quantities.
 
  ![preview](/client/src/assets/screenshots/Capture2.PNG "Preview Application")
  
  The transaction can be finalized through stripe.

  ![preview](/client/src/assets/screenshots/Capture3.PNG "Preview Application")

  ### Code snippets:
  
  - Reducer.js - included initialState
  
  ````js
  const initialState = {
  products: [],
  cart: [],
  cartOpen: false,
  categories: [],
  currentCategory: '',
  }
  ````
  ````js
  export const reducer = (state = initialState, action) => {
    ....
    }
  ````

 - App.js document - imported Provider
  ````js
  import { Provider } from 'react-redux';
  ````
  
 - Cart, CartItem, CategoryMenu, ProductItem, ProductList and Details page, included useDispatch and useSelector from react-redux::

  ````js
  import { useDispatch, useSelector } from 'react-redux'
  ````

  ````js
  const Cart = () => {
    const dispatch = useDispatch();
    const state = useSelector(state => state)
    ...

    }
  ````

  - Removed the following from the above documents and deleted GlobalState.js:

````js
import { useStoreContext } from '../../utils/GlobalState';
````
````js
const Cart = () => {
  const [state, dispatch] = useStoreContext();
  ....
}
````

  ## License
  [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
  
  This application is covered by MIT license, available at:
  https://opensource.org/licenses/MIT

  ## Contributing
  Please feel free to send a pull request, the following is my GitHub account: https://github.com/Renatatims

  ## Tests
  Please make sure to install all the packages before running the application. To run the application:
  ```
  npm run develop
  ```

  ## Questions
  If you have any questions please contact me at:
   - GitHub account:https://github.com/Renatatims
   - e-mail account: renatatims@gmail.com

  ## Credits
  https://redux.js.org/introduction/getting-started