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

    <!-- Toast -->
    <div class="position-fixed bottom-0 end-0 p-3" style="z-index: 111">
      <div id="liveToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true" data-bs-delay="10000">
        <div class="toast-header">
          <i class="fas fa-lightbulb me-2" />
          <strong class="me-auto">Tip</strong>
          <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close" />
        </div>
        <div class="toast-body">
          If the Y axis text is not clear, you can click on the bar or move the mouse to the top of the bar.
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Divider from './Divider.vue'
import Chart from './Chart.vue'
import { Toast } from 'bootstrap'

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
              fontSize: '8'
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
              fontSize: '8'
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
              fontSize: '8'
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

    const target = document.getElementById('skill')

    const toastLive = document.getElementById('liveToast')

    const callback = (entries, observer) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const toast = new Toast(toastLive)

          toast.show()
          observer.unobserve(target)
        }
      })
    }

    const options = {
      threshold: 0.8
    }

    const observer = new IntersectionObserver(callback, options)
    observer.observe(target)
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

  .btn:hover, .btn:focus {
    background-color: $dark-green;
    transform: scale(1.03);
  }

  .toast {
    background-color: $light-gray;
    width: 330px;
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

    .toast {
      width: 350px;
    }
  }
}
</style>