<template>
  <div class = "container">
    This is who you are!
    <div v-for="face in faces">       
     <img :src="'https://raw.githubusercontent.com/EmojiTwo/emojitwo/master/png/'+face.emoji.code+'.png'" width="90" height="90"/>
    </div>
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
            self.faces = response.data.characters;
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
