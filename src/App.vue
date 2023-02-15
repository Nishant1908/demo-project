<template>
  <UserDetails />
</template>

<script>
import UserDetails from "./components/UserDetails.vue";
export default {
  name: "App",
  components: {
    UserDetails,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: black;
  margin-top: 60px;
}
</style>
