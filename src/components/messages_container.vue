<template>
  <div class="messages_container">
    <h2 v-if="database.messages.length > 0">Here are all your thoughts</h2>
    <h2 v-else>Nothing to say to the world yet!</h2>
    <ul v-for="message in database.messages" :key="message.id">
      <li>{{message.value}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["database"]
};
</script>

<style scoped>
.messages_container ul li {
  list-style-type: none;
  border-bottom: 1px lightblue solid;
  padding-bottom: 20px;
  width: 85%;
}
.messages_container h2 {
  padding-left: 10%;
}
.messages_container ul {
  padding-left: 15%;
}
</style>