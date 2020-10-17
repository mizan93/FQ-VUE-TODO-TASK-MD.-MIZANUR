<template>
  <div class="hello">
    <h1>{{msg}}</h1>
    <div class="form-group">
      <input type="text" class="form-control" v-model="item" placeholder="add to list">
        <button type="submit" @click="addItemd">ADD</button>
        <div v-for="todo in todos" :key="todo.id" class="todo-item">
          <div>{{ todo.title}}</div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Todo List',
      item:'',
      idforTodo:3,
      todos:[
        {
          'id':1,
          'title':'First Item',
          'completed':false
        },
        {
          'id':2,
          'title':'Second Item',
          'completed':false
        },
      ],
    }
  },
  methods: {
    addItemd(){
      this.todos.push({
        id:this.idforTodo,
        title:this.item,
        completed:false
      })
      this.item='',
      this.idforTodo++

    }
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >

</style>
