<template>
    <div class="container">
      Disaster can strike at any time. Are you ready?
      <img src="../assets/SOS-title-graphic.png" width="400" height="180"/>

      <button>
        <img src="../assets/ifeelunlucky_btn.png" width="400" height="180"/> <!--route to  Story-->
      </button>
      <button> <!--route to info screen-->
        ?
      </button>

    </div>
</template>

<script>

var axios = require('axios')

export default {
  name: 'StartScreen',
  data () {
    return {
      game:{}
    }
  },
  methods: {
    startGame: function() {
      //call the router and webserver

    }
  },
  created(){
    this.startGame()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
