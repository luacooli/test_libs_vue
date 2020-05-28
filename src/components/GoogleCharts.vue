<template>
  <div class="google-chart">
    <GChart
      class="gchart1"
      type="ColumnChart"
      :data="graficResult1"
      :options="chartOptions1"
    />
    <GChart
      class="gchart2"
      type="ColumnChart"
      :data="graficResult2"
      :options="chartOptions2"
    />
  </div>
</template>

<script>
import { GChart } from 'vue-google-charts'

export default {
  name: 'GoogleCharts',
  components: {
    GChart,
  },
  data() {
    return {
      graficResult1: [['Leitos', 'Pacientes']],
      pacients1: [
        {
          leito: 'leito A',
          rotatividade: 7,
        },
        {
          leito: 'leito B',
          rotatividade: 10,
        },
        {
          leito: 'leito C',
          rotatividade: 5,
        },
        {
          leito: 'leito D',
          rotatividade: 6,
        },
      ],
      chartOptions1: {
        title: 'Total pacientes atendidos por filas',
        bar: { groupWidth: '10%' },
        colors: ['#00C59B'],
      },

      graficResult2: [['Leitos', 'Pacientes']],
      pacients2: [
        {
          leito: 'leito A',
          rotatividade: 14,
        },
        {
          leito: 'leito B',
          rotatividade: 1,
        },
        {
          leito: 'leito C',
          rotatividade: 20,
        },
        {
          leito: 'leito D',
          rotatividade: 8,
        },
      ],
      chartOptions2: {
        title: 'Total pacientes atendidos por filas',
        bar: { groupWidth: '10%' },
        colors: ['#0183C4'],
        legend: 'inside',
      },
    }
  },
  mounted() {
    this.pacients1.forEach((patient) => {
      const leito = [patient.leito, patient.rotatividade]
      this.graficResult1.push(leito)
    })

    this.pacients2.forEach((patient) => {
      const leito = [patient.leito, patient.rotatividade]
      this.graficResult2.push(leito)
    })
  },
}
</script>

<style>
.google-chart {
  height: 230px;
  width: 1234px;
}

.gchart1,
.gchart2 {
  margin: 50px 0;
}
</style>
