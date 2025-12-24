<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div id="app">
    <!-- Landing Section -->
    <section v-if="!opened" class="landing">
      <h1>You're Invited!</h1>
      <button @click="openInvitation">Click to Open</button>
    </section>

    <!-- Main Invitation -->
    <section v-else class="invitation">
      <h1>Welcome to the Celebration 🎉</h1>
      <p>Details of the event here...</p>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      opened: false
    }
  },
  methods: {
    openInvitation() {
      this.opened = true
    }
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: sans-serif;
  background: #fef6e4;
}
#app {
  text-align: center;
  padding: 50px;
}
.landing {
  background: #ffd6d6;
  padding: 100px 20px;
  border-radius: 20px;
}
.landing button {
  padding: 10px 20px;
  font-size: 18px;
  cursor: pointer;
}
.invitation {
  background: #d6ffd6;
  padding: 100px 20px;
  border-radius: 20px;
}
</style>

