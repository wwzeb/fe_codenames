<template>
  <div id="app">
    <div class="score">
      <Score 
        :teamName="teams.team1.name" 
        :score="teams.team1.score" 
        :color="teams.team1.color"
      ></Score>

      <Turn
        :turn="teams.team1.name"
        :color="teams.team1.color"
      ></Turn>

      <Score 
        :teamName="teams.team2.name" 
        :score="teams.team2.score" 
        :color="teams.team2.color"
      ></Score>
    </div>

    <div class="board">
      <GameBoard>

          <Codename 
              v-for="codename in codenames" 
              :key="codename.codename" 
              :codename="codename.codename"
              :type="codename.type"
              :increaseScore="increaseScore"
          ></Codename>

      </GameBoard>
    </div>
  </div>
</template>

<script>
import GameBoard from './components/GameBoard';
import Score from './components/Score';
import Codename from './components/Codename';
import Turn from './components/Turn';
import WordsFile  from 'raw-loader!./assets/words.txt';

export default {
  name: 'app',
  components: {
    GameBoard,
    Score,
    Codename,
    Turn
  },
  created: function() {
    const words = WordsFile.split('\n');
    let randomWords = [];
    while(randomWords.length <= 24){
      let randomNum = Math.floor(Math.random() * words.length) + 1;
      if(randomWords.indexOf(words[randomNum]) === -1) randomWords.push(words[randomNum]);
    }
    this.codenames = randomWords.map(word => {
      return {
        codename: word,
        type: this.selectRandomColor(this.types),
      }
    });
    let coinFlip = Math.round(Math.random()) + 1;
    this.teams["team" + coinFlip]["color"] = "red-team";
    this.teams["team" + ((coinFlip % 2) + 1)]["color"] = "blue-team";
  },
  methods: {
    increaseScore: function (col) {
      if (col === 'red') this.teams.team1.score++
      if (col === 'blue') this.teams.team2.score++
    },
    selectRandomColor: function (obj) {
      const typeArr = Object.keys(obj);
      let randomNum = Math.floor(Math.random() * typeArr.length);
      let randomKey = typeArr[randomNum];

      if (obj[randomKey] > 0) {
        for(let [key, value] of Object.entries(obj)) {
            if(key.toString() == randomKey) {
                obj[key] = value - 1
            }
        }
        this.types = {...obj};
        return randomKey;
      } else if (obj[randomKey] === 0) {
        delete this.types[randomKey]
        return this.selectRandomColor(this.types);
      }
    }
  },
  data () {
    return {
      teams: {
        team1 : {
          name: 'Team 1',
          score: 0
        },
        team2 : {
          name: 'Team 2',
          score: 0
        }
      },
      codenames: [],
      types: {
        red: 9,
        blue: 9,
        black: 1,
        neutral: 6
      }
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
  user-select: none;
}

.turn {
  display: flex;
  justify-content: center;
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
