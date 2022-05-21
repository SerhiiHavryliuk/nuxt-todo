<template>
  <!--  <Tutorial/>-->
  <main>
    <h1> Task Board</h1>
    <p> Create of list of tasks</p>

    <div class="create-new">
      <input
        @keypress.enter="addTask"
        placeholder="Add new task"
        type="text"
        v-model="newTask"
      >

      <button @click="addTask"> Add task</button>
    </div>

    <div class="tasks">
      <Task
        v-for="(task, i) in $store.state.tasks"
        :key="1"
        :task="task"/>
    </div>

  </main>


</template>

<script>
  export default {
    name: 'IndexPage',
    data() {
      return {
        newTask: ""
      }
    },
    methods: {
      addTask() {
        console.log(1111)
        if (this.newTask) {
          this.$store.commit('ADD_TASK', this.newTask);
          this.newTask = '';
        }
      }
    }
  }
</script>
