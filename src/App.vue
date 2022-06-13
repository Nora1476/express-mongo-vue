<template>
  <img alt="Vue logo" src="./assets/logo.png">
   <div id="userRegist-box">
       <UserRegist/>
   </div>

   <div id="userList-box">
       <UserList/>
   </div>

   <div id="commentRegist-box">
      <CommentRegist/>
   </div>

    <div id="commentList-box">
      <CommentList/>
   </div>

</template>

<script>
import UserRegist from './components/UserRegist.vue'
import UserList from './components/UserList.vue'
import CommentRegist from './components/CommentRegist.vue'
import CommentList from './components/CommentList.vue'

export default {
  name: 'App',
  components: {
     UserRegist, UserList,  CommentRegist, CommentList,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
