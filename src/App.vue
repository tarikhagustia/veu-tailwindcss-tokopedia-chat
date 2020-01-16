<template>
  <div id="app">
    <div class="container mx-auto">
      <ChatApp />
    </div>
  </div>
</template>

<script>
import ChatApp from './components/ChatApp.vue'

export default {
  name: 'app',
  components: {
    ChatApp
  }
}
</script>

<style>
body {
  @apply bg-gray-200
}
</style>
