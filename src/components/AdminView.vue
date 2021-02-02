<template>
  <div class="admin">
    <form action="">
      <p>
        Title <br />
        <input v-model="title" />
      </p>
      <p>
        Description <br />
        <input v-model="description" />
      </p>
      <p>
        Image URL <br />
        <input v-model="image" />
      </p>
      <button @click="handleSubmit">SUBMIT</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "AdminView",
  data() {
    return {
      id: 0,
      title: "",
      image: "",
      description: ""
    };
  },
  methods: {
    handleSubmit(event) {
      event.preventDefault(); //prevent the form from refreshing the page
      this.id++;
      this.$emit("createProject", {
        id: this.id,
        title: this.title,
        image: this.image,
        description: this.description
      });
      this.clear();
    },

    clear() {
      this.title = "";
      this.image = "";
      this.description = "";
    }
  }
};
</script>

<style>
.admin {
  background-color: chartreuse;
}
form {
  text-align: center;
  border: 2px solid chartreuse;
}
/* input {
    display: block;
  } */
</style>
