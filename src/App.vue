<template>
  <div id="app">
    <StartScreen>
    </StartScreen>
    <Story>
    </Story>
    <Disaster>
    </Disaster>
    <Gather>
    </Gather>
  </div>
</template>

<script>

import StartScreen from './components/StartScreen'
import Story from './components/Story'
import Disaster from './components/Disaster'
import Gather from './components/Gather'

export default {
  name: 'App',
  components: {
    StartScreen,
    Story,
    Disaster,
    Gather
  }
}
</script>

<style>

</style>
