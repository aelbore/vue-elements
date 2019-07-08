<template>
  <div id="app">
    <div style="text-align:center;margin-bottom:20px;">
      <h1>Welcome to Vue</h1>
      <img width="200" src="https://vuejs.org/images/logo.png" />
    </div>
    <div class="cards">
      <div v-for="(profile, index) in profiles" v-bind:key="index">
        <Card :profile="profile" />
      </div>
    </div>
  </div>
</template>

<script>
import Card from './Card.vue'

const getProfiles = () => {
  return [
    {
      name: "Jane Doe",
      profession: "Framework Developer",
      motto: "I never wanted to be famous, I wanted to be great.",
      photo: "https://pymwoqn637.codesandbox.io/default.png"
    },
    {
      name: "Kurtis Weissnat",
      profession: "Developer",
      motto: "When in doubt, iterate faster!",
      photo: "https://pymwoqn637.codesandbox.io/default.png"
    },
    {
      name: "Chelsey Dietrich",
      profession: "UX Developer",
      motto: "Genius is the ability to reduce the complicated to the simple.",
      photo: "https://pymwoqn637.codesandbox.io/default.png"
    },
    {
      name: "Leanne Graham",
      profession: "UI Developer",
      motto: "The key to performance is elegance, not battalions of special cases.",
      photo: "https://pymwoqn637.codesandbox.io/default.png"
    },
  ]
}

export default {
  name: 'app',
  components: {
    Card
  },
  data() {
    return {
      profiles: {
        ...getProfiles()
      }
    }
  }
}
</script>

<style>
.cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: auto;
  grid-gap: 1rem; 
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
