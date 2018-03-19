<template>
  <div id="app">
    <Skills/>
  </div>
</template>

<script>
import Skills from './components/Skills.vue'

export default {
  name: 'app',
  components: {
    Skills
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
