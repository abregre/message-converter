<template>
  <div class="container">
    <form @submit.prevent="convertString">
      <textarea
        v-model="inputMessage"
        class="inputMessage"
        maxlength="160"
      ></textarea>
      <button type="submit" class="convert-btn">Convert to basic L33t</button>
    </form>
    <div class="outputMessage">
      {{ outputMessage }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'MessageConverter',
  data() {
    return {
      inputMessage: '',
      outputMessage: ''
    }
  },
  methods: {
    convertString() {
      this.outputMessage = this.inputMessage
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  max-width: 600px;
  display: flex;
  flex-direction: column;
}
.inputMessage {
  width: 600px;
  max-width: 600px;
  height: 300px;
  max-height: 600px;
  font-size: 1.5rem;
  padding: 1rem;
  border: 1px solid #407076;
}
.convert-btn {
  font-size: 1.5rem;
  padding: 1rem 1.5rem;
  background-color: #dde1e4;
  color: #407076;
  border: none;
  border-radius: 10px;
  transition: all 0.15s ease-in-out;
}
.convert-btn:hover {
  background-color: #bdbfc0;
}
.convert-btn:active {
  transform: scale(0.9);
}
</style>
