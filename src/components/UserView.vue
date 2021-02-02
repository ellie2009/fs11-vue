<template>
  <div class="user">
    <!-- User View  -->
    <!-- <div class="content">  this goes with the original solution where each item is passed individually
      <img v-bind:src="image" alt="" />
    </div> -->
    <!-- <showcase @setShowcase="currProject"></showcase> -->
    <div><img class="large" :src="currProject.image" /></div>

    <!-- <p>{{ projects }}</p> -->
    <!-- <p>{{ message }}</p> -->
    <!-- <p :key="1">{{id}} {{ description }} something else</p> -->
    <div v-for="(project, i) in projects" :key="i">
      <img
        v-bind:src="project.image"
        v-on:click="event => updateShowcase(project.id)"
      />
    </div>
  </div>
</template>

<script>
import Showcase from "./Showcase";

export default {
  name: "UserView",
  components: {
    showcase: Showcase
  },

  data() {
    return {
      message: "Some test message",
      currProject: 0
    };
  },

  // props: ["id", "title", "description", "image"],
  props: ["projects"],

  methods: {
    updateShowcase(id) {
      for (let project in this.projects) {
        if (this.projects[project].id === id) {
          this.currProject = this.projects[project];
        }
      }
    }
  }
};
</script>

<style>
.user {
  background-color: coral;
  display: inline-block;
}
img {
  width: 200px;
  border-radius: 5px;
  margin: 10px;
}

.large {
  width: 700px;
}
</style>
