# SHINKAI - The Messaging App that doesn't get in your way

In this hyper-social media driven world, with apps competing for their share of your mind's attention, dopamine and your time, **Shinkai** is a messaging app focused on being as **calming, minimalist and as easy-to-use** as possible while still providing all the functional requirements:

1. **User Registration and Authentication**: Shinkai implements this using JWT
2. **One on One messaging**: Shinkai uses Socket.io for user to user messaging
3. **Group chat**
4. **Notifications**

## [Shinkai is deployed here](https://shinkai-chat-ckd6.vercel.app/)
## [Shinkai's backend is deployed here](https://shinkai-chat.onrender.com)



## Tech Stack

### Frontend

Shinkai's frontend is built on **React**. This is the complete list of technologies used:

1. **React**
2. **React Router DOM**: For navigation
3. **Socket.io-client**: Client-side socket.io library
4. **Axios**: For making HTTP requests
5. **Chakra UI and Chakra Icons (and dependencies)**: For UI components and icons.
6. **React Notification Badge**: For the notification icon.

### Backend

Shinkai's backend is built on **Node.js + Express + Socket.io**. Socket.io helps keep the connection between client and server alive once the handshake is done, and Node.js is the JS runtime, while Express is a framework to help ease the creation of servers-side apps. For the rest of the dependecies:

1. **MongoDB**: NoSQL database used for storage, picked because of excellent scaling capabilites, familiarity, fast development speed and DX.
2. **Mongoose**: ORM to interact with MongoDB.
3. **Bcrypt**: Hashing library to hash user's passwords before storing them in the database.
4. **cors**: for enabling Cross-Origin-Requests.
5. **jsonwebtoken**: Library for generating and verifying JSON Web Tokens (JWTs) used for authenticating clients.
6. **express-async-handler**: wrapper function to help handle errors in promises without writing boilerplate code.
7. **(devDependency) nodemon**: for automatically restarting the dev server if any changes are made to the code

## Setting up Shinkai

### Frontend

Open up your terminal, change into the directory where the `frontend` folder is located, and run the following command to install the dependencies:

```
npm install --legacy-peer-deps
```

- ***Note: the `--legacy-peer-deps` flag is being supplied because of two dependencies, `react-lottie` and `react-notification-badge`. While `npm` will warn you, those dependencies will not cause any issues with React 18, and are thus safe to use. Their source code uses nothing that will break due to changes introduced by React 18. I checked.***

Once the dependencies are installed, simply run:

```
npm run start
```

That should fire up a local server on `localhost:3000` with our app running!


### Backend

Open up your terminal, change into the directory where the `backend` folder is located, and run the following command to install the dependencies:

```
npm install
```

Inside the `backend` directory, you will also need to create a `.env` file with the following contents

```
PORT = 5000
MONGO_URI=""
JWT_SECRET = "makotoshinkaisporcorossowasamazing"
NODE_ENV = production
```

- ***Note: You will have to use the URI for you own MONGO DB Collection. The URI contains sensitive information, and is thus left blank in this example. It's also not a good idea to share your JWT secret key, but is being shared here for the purposes of this assignment.***

Once this is done, run:

```
node server.js
```

This will start the server on `localhost:5000`.


## Screenshots

![one-on-one messaging](img/one.png)
![side panel with notifications and user options](img/two.png)
![searching for users](img/three.png)
![creating a group chat](img/four.png)
