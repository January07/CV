<template>
  <div id="main" />
</template>

<script>
import * as echarts from 'echarts'

export default {
  name: "Chart",

  props: {
    chartData: {
      type: Object,
      required: true
    }
  },

  data() {
    return {
      option: this.chartData
    }
  },

  computed: {
    myChart() {
      // 基於準備好的 DOM，初始化 echarts 實例
      return echarts.init(document.getElementById('main'))
    }
  },

  mounted() {
    window.onresize = () => {
      this.myChart.resize()
    }
  },

  methods: {
    renderChart() {
      this.myChart.clear()
      this.myChart.setOption(this.option)
    }
  },

  watch: {
    chartData: {
      handler(newValue, oldValue) {
        this.option = newValue
        this.renderChart()
      }
    }
  }
}
</script>

<style lang="scss" scoped>
#main {
  height: 400px;
}
</style>