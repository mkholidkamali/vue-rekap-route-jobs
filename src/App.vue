<template>
  <nav>
    <router-link :to="{ name: 'home' }">Home</router-link> |
    <router-link :to="{ name:'about' }">About</router-link> |
    <router-link :to="{ name:'jobs' }">Jobs</router-link>
  </nav>

  <button @click="redirect">Redirect</button>
  <button @click="goBack">Go Back</button>
  <button @click="goForward">Go Forward</button>

  <router-view/>
</template>

<script>
export default {
  methods: {
    redirect() {
      this.$router.push({ name: 'home' })
    },
    goBack() {
      this.$router.go(-1)
    },
    goForward() {
      this.$router.go(1)
    }
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
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

nav a.router-link-exact-active {
  /* color: #42b983; */
  color: white;
  background: crimson;
  padding: 10px 15px;
  border-radius: 20px;
  text-decoration: none;
}

button {
  padding: 10px 15px;
  border-radius: 10px;
  border: 0px;
  margin: 5px;
  cursor: pointer;

}
</style>
