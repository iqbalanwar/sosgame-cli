<template>
<div>
    <head>
        The Disaster:
    </head>

    <body>
        <img src=""/>
        <p>A %disasterLevel% is predicted for the next week</p>

        <script>
            <p>The danger is %disasterDist%</p>
        </script>

        <button v-on:click="stay">
            Stay?
        </button>
        <button v-on:click="leave">>
            Leave?
        </button>
    </body>
</div>
</template>

<script>

var axios = require('axios')

export default {
  name: 'Story',
  data () {
    return {
      disasterPic:{},
      disasterLevel:{},
      disasterDist:{},
      disasterChoice: {
          stay: 0,
          leave: 1
      }
    }
  },
  methods: {
    disasterGame: function() {
        var self = this
        axios.get("http://s-o-s.fun/api/game/start")
            .then(function(response) {
            //var len = characters.length;
            //for (i = 0; i < len; i++) {
                self.disasterPic = response.data.disaster.emoji.url;
                self.disasterLevel = response.data.disaster.generated_level;
                self.disasterDist = response.data.disaster.distance;
            //}
            }
    },

    distChoice: function(event) {
        console.log(this.disasterChoice)
        //return this.disasterChoice
        axios.post('/game/disasterChoice', {
            stayOrGo: this.disasterChoice
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
