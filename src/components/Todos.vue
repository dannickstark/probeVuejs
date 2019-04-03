<template>
    <section class="todoapp">
      <header class="header">
        <h1>Todos</h1>
        <input @keyup.enter="addTodo" v-model="newTodo" type="text" class="new-todo" placeholder="Ajouter une tache">
      </header>
      <div class="main">
        <input type="checkbox" class="toggle" v-model="allDone">
        <ul class="todo-list">
          <li class="todo" v-for="(todo,id) in filteredTodo" :key="id" :class="{completed: todo.completed, editing: editing === todo}">
            <div class="view">
              <input class="toggle" type="checkbox" v-model="todo.completed">
              <label @dblclick="editTodo(todo)">{{ todo.name}}</label>
              <button class="destroy" @click="deleteTodo(todo)"></button>
            </div>
            <input type="text" class="edit" v-model="todo.name" @keyup.enter="doneEdit" @keyup.esc="cancelEdit" v-focus="todo === editing" @blur="doneEdit">
          </li>
        </ul>
      </div>
      <footer class="footer" v-show="hasTodo">
        <span class="todo-count"> <strong>{{remaining}}</strong> taches a faire  </span>
        <ul class="filters">
          <li><a href="#" :class="{selected: filter === 'all'}" @click.prevent="filter = 'all'">Toutes</a></li>
          <li><a href="#" :class="{selected: filter === 'todo'}" @click.prevent="filter = 'todo'">A faire</a></li>
          <li><a href="#" :class="{selected: filter === 'done'}" @click.prevent="filter = 'done'">Faites</a></li>
        </ul>
        <button class="clear-completed" @click.prevent="deleteCompleted" v-show="doneTodos">Supprimer les taches finies</button>
      </footer>
    </section>
</template>

<script>
import Vue from 'vue'
export default {
  name: 'Todos',
  data () {
    return {
      todos: [
        {
          name: 'Tache de test',
          completed: true
        }
      ],
      newTodo: '',
      filter: 'all',
      editing: null,
      oldTodo: ''
    }
  },

  computed: {
    remaining(){
      return this.todos.filter(todo => !todo.completed).length
    },
    filteredTodo(){
      if(this.filter === 'todo'){
        return this.todos.filter(todo => !todo.completed)
      } else if (this.filter === 'done') {
        return this.todos.filter(todo => todo.completed)
      } else {
        return this.todos
      }
    },
    allDone: {
      get(){
          return this.remaining === 0
      },
      set(value){
          this.todos.forEach(todo => { todo.completed = value})
      }
    },
    hasTodo (){
      return this.todos.length > 0
    },
    doneTodos () {
      return this.todos.filter(todo => todo.completed).length
    }
  },

  methods: {
    addTodo: function(){
      this.todos.push({
        name: this.newTodo ,
        completed: false
      })
      this.newTodo = ''
    },
    deleteTodo (todo) {
      this.todos = this.todos.filter(i => i!== todo)
    } ,
    deleteCompleted () {
      this.todos = this.todos.filter(todo => !todo.completed)
    },
    editTodo (todo) {
      this.editing = todo
      this.oldTodo = todo.name
    },
    doneEdit (){
      this.editing = null
    },
    cancelEdit (){
      this.editing = this.oldTodo
      this.doneEdit()
    }
  },

  directives:{
    focus (el, value){
      if (value){
        Vue.nextTick( () => {
          el.focus()
        })        
      }
    }
  }
}
</script>

<style src="./todos.css"></style>
