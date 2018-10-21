<template>
  <div class = "container">
    <img src=""/> <!--For the characters-->
    <button> Next </button>
  </div>
</template>

<script>

var axios = require('axios')

export default {
  name: 'Story',
  data () {
    return {
      faces:{}
    }
  },
  methods: {
    randomPlayer: function() {
      var self = this
      axios.get("http://s-o-s.fun/api/game/start")
        .then(function(response) {
          //var len = characters.length;
          //for (i = 0; i < len; i++) {
            self.faces = response.data.characters[0].emoji.url;
        //}
      })
    }
  },
  created(){
    this.randomPlayer()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
