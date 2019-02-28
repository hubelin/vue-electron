<template>
  <div class="home">
    <form @submit.prevent="addTask">
      <input v-model="task" type="text">
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
  data() {
    return {
      task: null
    };
  },
  computed: {
    tasks() {
      return this.$store.state.tasks;
    }
  },
  methods: {
    addTask() {
      this.$store.commit('addTask', this.task);
      this.tasks = null;
    }
  }
};
</script>
