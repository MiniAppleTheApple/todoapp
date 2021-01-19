<template>
  <div id="app">
    <h1>
      Todo List
    </h1>
    <div id="item" v-for="(todo,id) in todos" v-bind:key="todo">
        <button v-on:click="del(id)">
          {{ todo }}
        </button>
    </div>
    <button v-on:click="add()" id="add">add new</button>
    <input v-model="item">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {},
  data() {
    return {
      item: "",
      todos: []
    }
  },
  methods: {
    add(){
      if(this.item !== "" || this.item !== " ") this.todos.push(this.item)
    },
    del(id){
      let todos2 = [];
      let i;
      for(i = 0;i < this.todos.length;i++){
        if(i !== id) todos2.push(this.todos[i])
      }
      this.todos = todos2
    }
  }
}
</script>

<style>
@font-face{
  src: url(./assets/iosevka-regular.ttf);
  font-family: Iosevka
}
body{
  background-color: #E3FCFF;
}
*{
  font-family: Iosevka,Noto Sans TC;
}
#app {
  display: flex;
  flex-direction: column;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#item{
  display: flex;
  flex-direction: left;
  margin: 0 auto;
  padding: 0px 0px;
  border: 1px solid #2c3e50;
  border-radius: 20px;
  margin-bottom: 10px;
}
#app #add{
  margin-right: 20px;
  margin: 0 auto;
  padding: 3px 15px;
  border: 1px solid #2c3e50;
  border-radius: 20px;
  margin-bottom: 10px;
  background-color: rgba(255,255,255,0);
}
#app input{
  margin: 0 auto;
  padding: 10px 10px;
  border-radius: 20px;
  border: 1px solid #2c3e50;
  background-color: rgba(255,255,255,0);
}
#item button{
  background-color: rgba(255,255,255,0);
  border: none;
  padding: 15px 60px;
  border-radius: 20px;
}
#item:hover{
  background-color: #D0E9EB;
}

</style>
