<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <p v-if='isSwearWord' class='text-danger'>You typed a swear word!</p>
    <input type='text' class="form-control" v-model="body">

  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Victoria\'s Learning Vue!',
      body: 'It\'s pretty cool.'
    }
  },
  computed: {
    isSwearWord(){
      var hasSwear = true;
      var swears = ["fuck","shit","dick","cunt"];

      swears.some(function(swear){

        if (this.body.indexOf(swear) >= 0){
          hasSwear = true;
          return true;
        } else {
          hasSwear = false;
        }
      }.bind(this));

      return hasSwear;
    }
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
