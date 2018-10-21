<template>
<div>
    <head>
        The Disaster:
    </head>

    <body>
        <img src=""/>
        <p>A %disasterLevel% is predicted for the next week</p>
<!-- SCRIPTS ARE NOT ALLOWED!
        <script>
            <p>The danger is disasterDist</p>
        </script>
-->
        <button v-on:click="stay">
            Stay?
        </button>
        <button v-on:click="leave">
            Leave?
        </button>
    </body>
</div>
</template>

<script>

var axios = require('axios')

export default {
  name: 'Disaster',
  data () {
    return {
      disasterPic:{},
      disasterLevel:{},
      disasterDist:{},
      game_id: {
          stay: 0,
          leave: 1
      }
    }
  },

  methods: {
    disasterGame: function() {
        var self = this
        axios.get("http://s-o-s.fun/api/game/start")
            .then( function(response) {
                self.disasterPic = response.data.disaster.emoji.url;
                self.disasterLevel = response.data.disaster.generated_level;
                self.disasterDist = response.data.disaster.distance;
            })
    },

    distChoice: function(event) {
        var self = this
        console.log(this.game_id)
        //return this.disasterChoice
        axios.post('/game/disasterChoice', {
            game_id: this.game_id
        })
        .then(function(response) {
            console.log(response);
        })
        .catch(function (error) {
            console.log(error);
        });
    }
  },

  created(){
    this.disasterGame(),
    this.distChoice()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
