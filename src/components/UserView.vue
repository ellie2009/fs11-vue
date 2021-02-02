<template>
  <div class="user">
    <!-- User View  -->
    <div class="content">
      <img v-bind:src="image" alt="" />
    </div>
    <!-- <p>{{ message }}</p> -->
    <!-- <p :key="1">{{id}} {{ description }} something else</p> -->
  </div>
</template>

<script>
export default {
  name: "UserView",

  data() {
    return {
      message: "Some test message"
    };
  },

  props: ["id", "title", "description", "image"],

  methods: {}
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
</style>
