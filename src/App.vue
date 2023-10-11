<template>
<div class="toDoList">
  <my-dialog :show="false">

  </my-dialog>
  <task-form 
      @add="addTask" 
    />
  <task-list 
    :tasks="tasks" 
    @remove="removeTask"
  />
</div>
</template>

<script>
import TaskForm from '@/components/TaskForm'
import TaskList from '@/components/TaskList'
import MyDialog from './components/UI/MyDialog.vue'

export default {
  components: {
    TaskForm, TaskList,
    MyDialog
  },
  data() {
    return {
      tasks: [
            {id: 0, title: 'Create 5 comprehension and 5 coding tasks.'},
            {id: 1, title: 'Finish this Vue project.'}
      ],
    }
  },
  methods: {
      addTask(task) {
        this.tasks.push(task)
      },
      removeTask(task) {
        this.tasks = this.tasks.filter(t => t.id !== task.id)
      }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: Avenir,
}
*::selection {
    background-color: rgb(255, 164, 53);
}
body {
  padding-top: 70px;
  background-color: tomato;
}
</style>