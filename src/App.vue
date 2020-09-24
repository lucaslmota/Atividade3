<template>
  <div id="app">
    <Users/>
    <Todos/>
    <Photos/>
    <Comments/>
    <Posts/>
  </div>
</template>

<script>
import Users from './components/Users'
import Todos from './components/Todos'
import Photos from './components/Photos'
import Comments from './components/Comments'
import Posts from './components/Posts'

export default {
  name: 'App',
  components: {Users, Todos, Photos, Comments, Posts}
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
