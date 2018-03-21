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
          <input type="text" class="txt" name="item" placeholder="Life goal..." v-model="goal" v-validate="'min:5'">
          <p class="alert" v-if="errors.has('item')">{{ errors.first('item') }}</p>      
          <input v-else type="submit" class="btn" value="submit" v-on:click.prevent="addGoal()">
        </form>
      </div>
      <div class="col">
        <transition-group name="list" tag="p">
          <p class="life-container" 
            v-for="(data, index) in goals" :key='index' 
            v-on:click="removeGoal(index)">
            {{ data.goal }}
          </p>
        </transition-group>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Goals',
  data() {
    return {
      goal: '',
      goals: [
        { "goal": "Master Vue.js" },
        { "goal": "Run a marathon" }
      ]
    }
  },
  methods: {
    addGoal() {
      this.$validator.validateAll().then((res) => {
        if (res) {
          this.goals.push({goal: this.goal})
          this.goal = '';          
        }
      })
    },
    removeGoal(i) {
      this.goals.splice(i, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "http://cdn.jsdelivr.net/npm/animate.css@3.5.1";
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
  .list-enter-active {
    animation: bounce-in .5s;
  }
  .list-leave-active {
    animation: bounce-in .5s reverse;
  }

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

</style>
