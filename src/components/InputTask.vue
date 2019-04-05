<template>
    <div>
       <input class="new-todo" placeholder="O que precisa ser feito?"
            v-model="task.title" @keyup.enter="addTask"/>

        <ul>
            <li v-for="task in tasks" v-bind:key="task.title">{{ task.title }}</li>
        </ul>
    </div>
</template>

<script>
import { Task } from '../models/Task'
export default {
  data () {
    return {
      task : new Task(),
      tasks: []
    }
  },
  methods: {
    addTask () {
      let task = new Task()
      task.completed = this.task.completed
      task.title = this.task.title
      this.tasks.push(task)      
    }
  }
}
</script>
<style>
</style>
