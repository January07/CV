<template>
  <section id="skill">
    <div class="container">
      <h2 class="mb-0">SKILL</h2>
      <Divider v-bind:color="'#2C3E50'" />
      <div class="col-12 col-md-10 col-xl-8 mx-auto">
        <Chart v-bind:chartData="chartData" />
      </div>
      <button class="btn mx-md-4" v-on:click="changeData(0)">Front-End</button>
      <button class="btn mx-1 mx-md-4" v-on:click="changeData(1)">Back-End</button>
      <button class="btn mx-md-4" v-on:click="changeData(2)">App & Else</button>
    </div>
  </section>
</template>

<script>
import Divider from './Divider.vue'
import Chart from './Chart.vue'

export default {
  name: "Skill",

  components: {
    Divider,
    Chart
  },

  data() {
    return {
      chartData: {},
      items: [
        {
          title: {
            text: 'Front-End skills'
          },
          tooltip: {},
          legend: {
            data: ['skill level'],
            right: '10%'
          },
          dataset: {
            source: [
                ['product', 'score'],
                ['Vue.js', '5'],
                ['jQuery', '5'],
                ['JS/TS', '6'],
                ['RWD', '8'],
                ['SCSS', '8'],
                ['HTML', '9']
            ]
          },
          xAxis: {},
          yAxis: {
            axisLabel: {
              textStyle: {
                fontSize: '8'
              }
            },
            type: 'category'
          },
          series: [
            {
              name: 'skill level',
              type: 'bar',
              encode: {
                x: 'score',
                y: 'product'
              }
            }
          ]
        },
        {
          title: {
            text: 'Back-End skills'
          },
          tooltip: {},
          legend: {
            data: ['skill level'],
            right: '10%'
          },
          dataset: {
            source: [
                ['product', 'score'],
                ['RESTful', '7'],
                ['MySQL', '7'],
                ['Laravel', '6'],
                ['Slim', '6'],
                ['PHP', '9'],
                ['Node.js', '5']
            ]
          },
          xAxis: {},
          yAxis: {
            axisLabel: {
              textStyle: {
                fontSize: '8'
              }
            },
            type: 'category'
          },
          series: [
            {
              name: 'skill level',
              type: 'bar',
              encode: {
                x: 'score',
                y: 'product'
              }
            }
          ]
        },
        {
          title: {
            text: 'App & Else skills'
          },
          tooltip: {},
          legend: {
            data: ['skill level'],
            right: '10%'
          },
          dataset: {
            source: [
                ['product', 'score'],
                ['Firebase', '7'],
                ['Yarn', '7'],
                ['AWS', '4'],
                ['Git', '7'],
                ['Kotlin', '6'],
                ['Android', '9']
            ]
          },
          xAxis: {},
          yAxis: {
            axisLabel: {
              textStyle: {
                fontSize: '8'
              }
            },
            type: 'category'
          },
          series: [
            {
              name: 'skill level',
              type: 'bar',
              encode: {
                x: 'score',
                y: 'product'
              }
            }
          ]
        }
      ]
    }
  },

  mounted() {
    this.chartData = this.items[0]
  },

  methods: {
    changeData(index) {
      this.chartData = this.items[index]
    }
  }
}
</script>

<style lang="scss" scoped>
section {
  padding: 7rem 0;

  h2 {
    font-weight: 700;
    font-size: 2.25rem;
    line-height: 2rem;
  }

  .btn {
    color: white;
    background-color: $light-green;
    font-weight: 700;
    box-shadow: none;
  }

  .btn:hover {
    background-color: $dark-green;
  }
}

@media (min-width: 992px) {
  section {
    h2 {
      font-size: 3rem;
      line-height: 2.5rem;
    }

    .btn {
      font-size: 1.25rem;
      padding: 0.5rem 1rem;
    }
  }
}
</style>