<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <my-echart></my-echart>
    <pei-chart></pei-chart>
    <asynchronous></asynchronous>
    <data-zoom></data-zoom>
    <visual-map></visual-map>
    <air></air>
  </div>
</template>

<script>

import MyEchart from './myechart.vue'
import PeiChart from './peichart.vue'
import Asynchronous from './asynchronous.vue'
import DataZoom from './datazoom.vue'
import VisualMap from './visualmap.vue'
import Air from './air.vue'

export default {
  name: 'hello',
  data () {
    return {
      msg: 'echarts'
    }
  },
  components:{
    MyEchart,
    PeiChart,
    Asynchronous,
    DataZoom,
    VisualMap,
    Air
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}


</style>
