<template>
  <div class="container">
    <Header title="Task Tracker" />
    <AddTask />
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>

import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks: []
    }
  },

  methods: {
    deleteTask(id) {
      if (confirm('are you sure?')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
        console.log("task", id)
      }
    },
    toggleReminder(id) {
      console.log('toggle', id)
      this.tasks = this.tasks.map((task) => task.id === id ? { ...task, reminder: !task.reminder } : task)
    }
  },

  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctor appointment',
        day: 'March 1st at 2:30pm',
        reminder: true
      },
      {
        id: 2,
        text: 'Meeting at school',
        day: 'March 3rd at 1:30pm',
        reminder: true
      },
      {
        id: 3,
        text: 'Food shopping',
        day: 'March 3rd at 11:00am',
        reminder: false
      }
    ]
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  cursor: pointer;
  padding: 10px 20px;
  display: inline-block;
  border: none;
  margin: 5px;
  border-radius: 5px;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
  background: #000;
  color: #fff;
}
</style>
