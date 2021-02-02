<template>
  <div>
    <h1>Hello World</h1>
    <!-- 
  <ul>
    <li v-for="project in this.allProjects" :key="project.title"> {{ project.title }}</li
  ></ul> -->

    <button @click="isAdmin = true" v-bind:class="{ cssAdmin: isAdmin }">
      ADMIN
    </button>
    <button @click="isAdmin = false" v-bind:class="{ cssUser: !isAdmin }">
      USER
    </button>

    <div>
      <admin-view v-if="isAdmin" @createProject="addProject" />
      <user-view v-else v-bind:projects="allProjects" />
      <!-- v-for="project in allProjects"
        v-bind:key="project.id"
        v-bind:id="project.id"
        v-bind:title="project.title"
        v-bind:description="project.description"
        v-bind:image="project.image" -->

      <!-- what does the key do??? -->
    </div>
  </div>
</template>

<script>
import AdminView from "./components/AdminView";
import UserView from "./components/UserView";

export default {
  name: "app",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    return {
      isAdmin: true,
      allProjects: []
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    }
  }
};
</script>

<style>
body {
  font-family: Arial, Helvetica, sans-serif;
  width: 800px;
  background-color: brown;
  margin: auto;
  text-align: center;
}
.cssAdmin {
  background-color: chartreuse;
}

.cssUser {
  background-color: coral;
}
</style>
