# messaging-app-websocket-client

A Client-App that can dispatch/receive messages to-&-from [Websocket-Server](https://github.com/knshetty/ping-pong-websocket-akkahttp-java) (**Note!** This "Echo-Service" is an Akka-HTTP streams based implementation)

## HowTo use this App

- Type your message in the provided **text-field** & press enter to disptach messages over the Websocket to an "Echo-Service"
- **Note!** Dispatching "ping" as a message, the response is bound to be "pong". However, anyother sequence of text-string as a messages will be a "plan-old echo" response from the websocket-server.
- Incoming messages (i.e. response) from the websocket-server (i.e. Echo-Service) will appear/listed below the **input text-field**

## Future (ToDo)
- ~~Dispatch & receive messages between "Echo-Service" hosted on Heroku cloud platform (i.e. Heroku-App)~~
- UX: Visualise initial connection establishment between this client & the websocket Echo-Service
- UX: Visualise the current Websocket connection status
- Dispatch Keep-Alive ping to the Echo-Service
- UX: Visualise the Keep-Alive ping activity
- New View: Sequence-Diagram visualisation (i.e. near realtime visualistion) of the data-traffic between this client & Echo-Service 

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Deploy to gh-pages
```
npm run deploy
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
