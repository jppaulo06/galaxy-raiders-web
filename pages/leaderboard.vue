<template>
  <div id="screen">
    <h1> Leaderboard </h1>
    <div v-for="game in Leaderboard" class="option">
      {{ game.date }}&nbsp; - &nbsp; <span style="color: #11F228">  {{ game.score }} </span>
    </div>
  </div>
</template>

<script>

import leaderboardJson from '../assets/LeaderboardMock.json'

export default {
  data () {
    return {
      Leaderboard: leaderboardJson
    }
  }
}

</script>

<style scoped>
  #screen {
    height: 100vh;
    width: 100vw;
    display: flex;
    position: fixed;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: white;
    background-color: #36bbf5;
  }

  .option {
    padding: 0.3em;
    margin: 0.3em;
    font-size: 2em;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #0E2CC0;
  }

  a {
    color: white;
    text-decoration: inherit;
  }

</style>
