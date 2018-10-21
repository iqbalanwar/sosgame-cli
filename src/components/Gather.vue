<template>
  <div>
    <head>
        <h3>Get Prepared</h3>
        <p>Select the items you need to collect in advance to be
            ready for the disaster</p>
    </head>
    <body>

    </body>
  </div>
</template>

<script>

var axios = require('axios')

export default {
  name: 'Gather',
  data () {
    return {
      list:{}
    }
  },
  methods: {
    gather: function() {
      var self = this
      axios.get("http://s-o-s.fun/api/game/decisions")
        .then(function(response) {
          //var len = characters.length;
          //for (i = 0; i < len; i++) {
            self.list = response.data.characters[0].emoji.url;
        //}
      })
    }
  },
  created(){
    this.gather()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
