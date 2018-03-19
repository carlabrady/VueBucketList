<template>
  <div class="hello">
    <div class="container color-dark">
      <div class="col">
        <p>Add a bucket list item</p>
      </div>
      <div class="col">
        <p>Your bucket list</p>
      </div>
    </div>

    <div class="container color-light">
      <div class="col">
        <p class="sm">Use this form to add a goal</p>

        <form>
          <input type="text" class="txt" name="item" placeholder="Life goal...">
          <input type="submit" class="btn" value="btnText">      
        </form>
      </div>
      <div class="col">
        <p class="life-container" v-for="(data, index) in skills" :key='index'>{{ data.skill }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      skills: [
        { "skill": "Vue.js" },
        { "skill": "Frontend Developer" }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
    display: grid;
    grid-template-columns: 50% auto;
}
.col {
    padding: .4em 1.3em;
}
.color-dark {
    background: #2885C4;
}
.color-light {
    background: #57B3F1;
}
input.txt {
    border: 0;
    padding: 1em;
    width: 80%;
    margin-bottom: 2em;
}
input.btn {
    border: 0;
    display:block;
    padding:1em 3em;
    background: #A5F883;
    color:#003A61;
    margin-bottom:1em;
    cursor:pointer;
}
.life-container {
    background: #3FA0E1;
    padding: 1em;
    font-weight: bold;
    cursor: pointer;
}

</style>
