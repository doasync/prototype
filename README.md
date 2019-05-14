# Implementation prototype requirements

## Demo

https://codesandbox.io/s/kk3yxy13l5

## State description

- Loading - fake loading, bound to 5-second timer.

- Listening - fake BT device listening, Discovery of 3 fake devices is imitated, each one with 3-second delay, after that devices start disappearing one-by one starting with the first one with 3-second delay each. Rinse and repeat from start. Listening routine should be started on state entry and stopped on state exit. Tapping a device results in switching to connecting to that device (Thus stopping discovery etc.).

- Connecting - fake BT device connection state. Connection process lasts for 5 seconds and may result either in successful connection (50% probability) or failure otherwise.

- Communication - fake BT message listening. On entry a message listening routine is started, simulating receiving of 1 text message (50 characters of lorem ipsum) at random interval (1-5 seconds). On state exit the routine should be stopped.

- Clean - no message is received, the next message received by the parent state is accepted and displayed switching to the "Message displayed" state.

- Message displayed - a message is displayed, allowing the user to accept it. any message received by the parent state is dropped (this state does not accept messages).

- At any moment during the application execution a "Quit" action is provided, allowing to terminate the application, invoking any current state/substate exit actions, thus stopping device listening/message listening routines.

## Design

The UI should contain controls, allowing to execute the supported actions, the rest should be minimized. Listening state should display the list of currently "discovered" devices.

## State chart

![State Chart](https://i.imgur.com/m1IAH8B.png "State Chart")

---

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br>
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
