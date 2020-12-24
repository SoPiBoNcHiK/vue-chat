<template>
  <div class="container">
      <ChatWindow :chatInfo="chatInfo"/>
  </div>
</template>



<script>
import ChatWindow from "./ChatWindow"

export default {
  name: "Container",
  components: {
      ChatWindow,
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