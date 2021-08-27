<template>
  
  <div>
    <h1>H</h1>
    <!-- <Home Hello_msg='HW'/> -->
    <!-- <HelloWorld msg="HO"/> -->
    <!-- <TodoList newmsg/> -->
    <!-- <TodoList msh/> -->
    <TodoList />
  </div>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Home from './components/Hello.vue'
import TodoList from './components/TodoList.vue'

export default {
  name: "App",
  components:{
    // HelloWorld,
    // Home,
    TodoList,
  }

};
</script>

<style>

body{
  background-color: rgb(66, 66, 66) ;
  color: aliceblue;
}

</style>


