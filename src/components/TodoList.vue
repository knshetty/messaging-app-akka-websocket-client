<template>
  <div>
    <BaseInputText
      v-model="newTodoText"
      placeholder="Message the server"
      @keydown.enter="dispatchMsgToWebsocketServer"
    />
    <ul v-if="todos.length">
      <TodoListItem
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @remove="removeTodo"
      />
    </ul>
    <p v-else>Incoming messages from Websocket-Server will be listed here.</p>
  </div>
</template>

<script>
import BaseInputText from "./BaseInputText.vue";
import TodoListItem from "./TodoListItem.vue";

let nextTodoId = 1;

export default {
  components: {
    BaseInputText,
    TodoListItem,
  },
  data() {
    return {
      newTodoText: "",
      todos: [],
      connection: null,
      msg: "",
    };
  },
  methods: {
    dispatchMsgToWebsocketServer() {
      const trimmedText = this.newTodoText.trim();
      if (trimmedText) {
        this.sendMsgToWebsocketServer(trimmedText);
        this.newTodoText = "";
      }
    },
    removeTodo(idToRemove) {
      this.todos = this.todos.filter((todo) => {
        return todo.id !== idToRemove;
      });
    },
    sendMsgToWebsocketServer(msg) {
      this.connection.send(msg);
    },
    addTodos(msg) {
      if (msg) {
        this.todos.unshift({
          id: nextTodoId++,
          text: msg,
        });
      }
    },
    getTimeStamp() {
      return new Date(new Date().getTime()).toLocaleString();
    }
  },
  created: function () {
    
    const websocketEchoService = 'echo';

    // Server - Local server (for testing purpose only)
    let serverAddress = 'localhost:8080';

    // Server - Heroku App (hosted on Heroku0 cloud)
    serverAddress = 'echo-websocket-akkahttp-java.herokuapp.com';
    
    // Build websocket-endpoint uri
    const echoWebsocketEndpointUri = 'wss://' + serverAddress + '/' + websocketEchoService;

    // Connect to websocket endpoint
    console.log('Establishing connection with the Websocket Server(' + echoWebsocketEndpointUri + ')...');
    this.connection = new WebSocket(echoWebsocketEndpointUri);

    this.connection.onopen = function (event) {
      console.log(event);
      console.log("Connection to Websocket Server has been established.");
    };
  },
  mounted: function mounted() {
    var addTodos = this.addTodos;
    this.connection.onmessage = function (event) {
      //console.log(event);
      console.log(event.data);
      addTodos(event.data);
    };
  },
};
</script>