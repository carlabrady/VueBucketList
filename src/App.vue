<template>
  <div id="app">
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/about">About</router-link></li>
    </ul>

    <router-view/>
  </div>
</template>

<script>
import Goals from './components/Goals.vue'

export default {
  name: 'app',
  components: {
    Goals
  }
}
</script>

<style>
@import url('http://fonts.googleapis.com/css?family=Raleway:300,700');

body {
    background:#2E9CE6;
    padding: 3em;
    font-family: 'Raleway', 'Arial';
    color: #fff;
}
ul {
    list-style-type:none;
    margin:0 0 2em 0;
    padding:0;
}
ul li {
    display:inline;
    margin-right: 30px;
}
ul li a {
    font-size: 1.5em;
}
a {
    color:#fff;
    text-decoration:none;
}
</style>
