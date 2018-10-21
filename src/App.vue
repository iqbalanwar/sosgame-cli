<template>
  <div id="app">
    <StartScreen>
    </StartScreen>
    <Story>
    </Story>
    <Disaster>
    </Disaster>
  </div>
</template>

<script>

import StartScreen from './components/StartScreen'
import Story from './components/Story'
import Disaster from './component/Disaster'

export default {
  name: 'App',
  components: {
    StartScreen,
    Story,
    Disaster,
  }
}
</script>

<style>

</style>
