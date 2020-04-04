<template>
  <div id="app">
    <HelloWorld />
    <ProgressBar 
    :playerhealth="playerhealth"
    :monsterhealth="monsterhealth"
    />
    <GameArea 
    v-if="isGameRunning"
    :attack="attack"
    :specialattack="specialattack"
    :heal="heal"
    :giveup="giveup"
    />
    <StartGame
    v-else
    :startgame="newGame"
    />

    <logs
    :logs="logs"
    />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ProgressBar from './components/ProgressBar.vue'
import GameArea from './components/GameArea.vue'
import StartGame from './components/StartGame.vue'
import logs from './components/logs.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ProgressBar,
    GameArea,
    StartGame,
    logs
  },
  data() {
    return{
      isGameRunning: false,
      playerhealth: 100,
      monsterhealth: 100,
      logs : [],
    }
  },
  methods : {
    newGame() {
      this.isGameRunning = true
      this.monsterhealth = 100
      this.playerhealth = 100
    },
    attack(){
      var damagebyplayer = Math.max((Math.floor(Math.random()*10) + 1),3)
      this.monsterhealth-=damagebyplayer

      this.logs.unshift({
        isplayer: true,
        text: "Player does an attack of " + damagebyplayer + " HP"
      })

      if(this.monsterhealth<0)
      {
        this.monsterhealth = 0
        alert('You won!')
        this.isGameRunning = false
      }
      this.monsterattack()
      
    },
    specialattack(){
      var damagebyplayer = Math.max((Math.floor(Math.random()*20) + 1),10)
      this.monsterhealth-=damagebyplayer

      this.logs.unshift({
        isplayer: true,
        text: "Player does an special attack of " + damagebyplayer + " HP"
      })

      if(this.monsterhealth<0)
      {
        this.monsterhealth = 0
        alert('You won!')
        this.isGameRunning = false
      }
      this.monsterattack()
    },
    heal(){
      if(this.playerhealth<90){
        this.playerhealth+=10
      }
      else{
        this.playerhealth=100
      }

      this.logs.unshift({
        isplayer: true,
        text: "Player heals 10 HP"
      })
      this.monsterattack()
    },
    giveup(){
      this.isGameRunning = false
    },
    monsterattack(){
      var attackbymonster = Math.max((Math.floor(Math.random()*15) + 1),5)
      this.playerhealth-=attackbymonster

      this.logs.unshift({
        isplayer: false,
        text: "Monster does an attack of " + attackbymonster + " HP"
      })

      if(this.playerhealth<0)
      {
        this.playerhealth = 0
        alert('You lost!')
        this.isGameRunning = false
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
