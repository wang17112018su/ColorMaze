<template>
  <div id="app" class="app">
    <StartPanel v-if="condition === -1"  v-on:restart="updateCondition($event)"></StartPanel>
    <BlackRedPanel v-else-if="condition === 2" v-on:restart="updateCondition($event)"></BlackRedPanel>
    <WhiteOrangePanel v-else-if="condition === 3" v-on:restart="updateCondition($event)"></WhiteOrangePanel>
    <GreenOrangeBlackPanel v-else-if="condition === 4" v-on:restart="updateCondition($event)"></GreenOrangeBlackPanel>
    <you-win v-else-if="condition === 1" v-on:restart="updateCondition($event)"></you-win>
    <you-lose v-else-if="condition === 0" v-on:restart="updateCondition($event)"></you-lose>
  </div>
</template>

<script>

import StartPanel from "./components/StartPanel";
import BlackRedPanel from "./components/BlackRedPanel";
import WhiteOrangePanel from "./components/WhiteOrangePanel";
import GreenOrangeBlackPanel from "./components/GreenOrangeBlackPanel";
import YouWin from "./components/YouWin";
import YouLose from "./components/YouLose";

export default {
  name: 'app',
  data() {
    return {
      condition : -1
    }
  },
  components: {
    YouLose,
    YouWin,
    GreenOrangeBlackPanel,
    WhiteOrangePanel,
    BlackRedPanel,
    StartPanel,

  },
  methods: {

    updateCondition(updatedCondition){
      this.condition = updatedCondition
    },

    add(){
      this.condition++
    },

  },


}
</script>

<style>
  .app {
    padding: 25px;
    text-align: center;
  }








</style>
