<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- http://192.168.2.33:3001/Users -->
    {{ test }}
    <!-- <ul>
      <li v-for="user in users" :key="user.id">{{ user.name }}</li>
    </ul>-->
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      users: [],
      test: ''
    }
  },
  mounted() {
    // fetch('http://192.168.2.33:3001/Users')
    //   .then(response => response.json())
    //   .then(data => this.users = data);
    fetch('http://192.168.2.33:8000/api/json')
      .then(response => response.json())
      .then(data => this.test = data);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
