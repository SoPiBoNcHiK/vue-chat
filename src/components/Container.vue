<template>
  <div class="container">
      <ChatMessage :username="chatInfo.username" :datetime="chatInfo.datetime" />
  </div>
</template>



<script>
import ChatMessage from './ChatMessage.vue'

export default {
  name: "Container",
  components: {
      ChatMessage,
  },
  props: ['chatInfo'],
};
</script>

<style>
.container {
  width: 764px;
  margin: auto;
  box-shadow: 0 0 15px 0 #5f5f5f73;
}
</style>