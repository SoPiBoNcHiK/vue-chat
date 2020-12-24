<template>
  <div id="app">
    <Container>
      <ChatWindow>
        <ChatMessage
          v-for="(message, i) in messages"
          v-bind:key="i"
          v-bind:username="message.author"
          v-bind:datetime="message.datetime"
        >
          {{ message.text }}
        </ChatMessage>
      </ChatWindow>
    </Container>
  </div>
</template>

<script>
import Container from "./components/Container.vue";
import ChatWindow from "./components/ChatWindow.vue";
import ChatMessage from "./components/ChatMessage.vue";

export default {
  name: "App",
  components: {
    Container,
    ChatWindow,
    ChatMessage,
  },
  data() {
    return {
      messages: [
        { username: "Ivan", datetime: "20.04.20", text: "Hello" },
        { username: "Ivan", datetime: "20.04.20", text: "Hello" },
      ],
      temp: [],
    };
  },
  methods: {
    getMessages() {
      this.axios
        .get("http://37.77.104.246/api/chat/getmessages.php")
        .then((response) => {
          this.messages = response.data;
        });
    },
  },
  mounted() {
    this.getMessages();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
