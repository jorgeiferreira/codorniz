<template>
  <div class="messages_container">
    <input
      class="writter"
      type="text"
      placeholder="Do you think about anything..."
      v-model="message"
      @keyup.enter="addNewMessage"
      :maxlength="max"
    />
    <button class="save" type="button" @click="addNewMessage">Say it</button>
    <div class="showlimit" v-text="max-message.length"></div>
  </div>
</template>

<script>
export default {
  props: ["database"],
  data() {
    return {
      message: "",
      max: 280
    };
  },
  methods: {
    addNewMessage() {
      var messages = this.database.messages;
      messages.push({
        id: messages.length + 1,
        value: this.message
      });
      this.message = "";
    }
  }
};
</script>

<style scoped>
.messages_container {
  background: lightblue;
  width: 500px;

  margin: auto;
  width: 80%;
  padding: 10px;
}
.messages_container .writter {
  height: 30px;
  width: 80%;
  font-size: 16px;
}

.messages_container .save {
  margin-left: 10px;
  height: 36px;
  font-size: 16px;
}
</style>