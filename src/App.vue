<template>
  <div id="app">
    <div class="logo-container">
      <img alt="Vue logo" class="logo" src="./assets/logo.jpg" />
      <h1>Codorniz</h1>
    </div>
    <create_message :database="database" />
    <messages_container :database="database" />
  </div>
</template>

<script>
import create_message from "./components/create_message.vue";
import messages_container from "./components/messages_container.vue";

export default {
  name: "App",
  components: {
    messages_container,
    create_message
  },
  data() {
    return {
      database: {
        messages: []
      }
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;

  margin: auto;
  width: 50%;
  padding: 10px;
}
#app .logo-container {
  text-align: center;
}

#app .logo {
  height: 120px;
}
</style>
