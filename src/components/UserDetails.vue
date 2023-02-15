<template>
  <div>
    <input type="text" placeholder="Search" v-model="searchValue" />
    <div v-if="usersList.length">
      <div v-for="(user, index) in usersList" :key="index">
       {{index+1}}. {{ user.name }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserDetails",
  data: () => ({
    searchValue: "",
    users: [],
  }),
  created() {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((response) => response.json())
      .then((data) => (this.users = data));
  },
  computed: {
    usersList() {
      if (this.searchValue.trim().length > 0) {
        return this.users.filter((user) =>
          user.name
            .toLowerCase()
            .includes(this.searchValue.trim().toLowerCase())
        );
      }
      return this.users;
    },
  },
};
</script>

<style scoped></style>
