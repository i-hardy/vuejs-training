<template>
  <li class="list-group-item">
    {{ task.description }}
    <!--- @click is shorthand for v-on:click
          any v-on: events can be prepended with an @ instead -->
    <button class="btn btn-danger btn-xs"
            @click="deleteTask">
      Delete Task
      <span class="glyphicon glyphicon-remove"></span>
    </button>
  </li>
</template>

<script>
  export default {
    props: ['task', 'board'],
    data() {
      return {};
    },
    methods: {
      deleteTask() {
        // Send a message to the parent component to delete a task
        this.$dispatch('deleteTask', this.task.id);
      },
    },
  };
</script>

<style>
  li button {
    float: right;
  }
</style>
