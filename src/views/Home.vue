<template>
  <div class="home">
    <h3>Task manager</h3>
    <!-- <form @submit.prevent="addTask">
      <input v-model="task" type="text" />
      <button type="submit">Submit</button>
    </form>-->
    <hr />
    <h3>Tasks</h3>
    <ul>
      <li v-for="(item, index) in tasks" :key="index">{{ item }}</li>
    </ul>
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
