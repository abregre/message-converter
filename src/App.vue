<template>
  <div class="app">
    <message-converter class="converter" />
  </div>
</template>

<script>
import MessageConverter from '@/components/MessageConverter'

export default {
  name: 'App',
  components: {
    MessageConverter
  }
}
</script>

<style>
body,
html {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>
