<template>
  <div id="app">
    <div class="score">
      <Score 
        :teamName="teams.team1.name" 
        :score="teams.team1.score" 
        :color="'red-team'"
      ></Score>

      <Score 
        :teamName="teams.team2.name" 
        :score="teams.team2.score" 
        :color="'blue-team'"
      ></Score>
    </div>

    <div class="board">
      <GameBoard>
        
          <Codename 
              v-for="codename in codenames" 
              :key="codename.codename" 
              :codename="codename.codename"
          ></Codename>

      </GameBoard>
    </div>
  </div>
</template>

<script>
import GameBoard from './components/GameBoard';
import Score from './components/Score';
import Codename from './components/Codename';

export default {
  name: 'app',
  components: {
    GameBoard,
    Score,
    Codename
  },
  data () {
    return {
      teams: {
        team1 : {
          name: 'team 1',
          score: 0
        },
        team2 : {
          name: 'team 2',
          score: 0
        }
      },
      codenames: [
        {
          codename: 'table',
          type: 'red'
        },
        {
          codename: 'cat',
          type: 'blue'
        },
        {
          codename: 'dress',
          type: 'neutral'
        },
        {
          codename: 'moon',
          type: 'black'
        },
        {
          codename: 'lamp post',
          type: 'neutral'
        },
        {
          codename: 'apple',
          type: 'neutral'
        },
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.board {
  display: flex;
  justify-content: center;
}

.score {
  display: flex;
  justify-content: space-around;
}
</style>
