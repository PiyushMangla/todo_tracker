<template>
  <nav>
    <router-link :to="{ name: 'project' }">Projects</router-link>
    <router-link to="/addProject">Add a new Project</router-link>
  </nav>
  <router-view />
</template>

<script>
import { todoMixin } from "./components/todoMixin";
export default {
  name: "App",
  mixins: [todoMixin],
  mounted() {
    localStorage.setItem("todoLists", JSON.stringify(this.todoList));
  },
};
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
  color: #959da1;
  margin-right: 20px;
  font-size: 25px;
  text-decoration: none;
  font-weight: 400;
}

nav a.router-link-active {
  border-bottom: 2px solid #19d4be;
}
</style>
