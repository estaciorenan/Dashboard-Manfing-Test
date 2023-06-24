<template>
  <Doughnut :chart-options="chartOptions" :chart-data="chartData" :chart-id="chartId" :dataset-id-key="datasetIdKey"
    :plugins="plugins" :css-classes="cssClasses" :styles="styles" :width="width" :height="height" />
</template>

<script>
import { Doughnut } from "vue-chartjs/legacy";
import Products from '../data/topProduto.json';

import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  ArcElement,
  CategoryScale,
} from "chart.js";

ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale);
export default {
  name: "DoughnutChart",
  components: {
    Doughnut,
  },
  props: {
    chartId: {
      type: String,
      default: "doughnut-chart",
    },
    datasetIdKey: {
      type: String,
      default: "label",
    },
    width: {
      type: Number,
      default: 400,
    },
    height: {
      type: Number,
      default: 200,
    },
    cssClasses: {
      default: "",
      type: String,
    },
    styles: {
      type: Object,
      default: () => { },
    },
    plugins: {
      type: Array,
      default: () => [],
    },
  },

  data() {
    return {

      chartData: {
        datasets: [
          {
            backgroundColor: ["#312775", "#4B4BF9", "#FF3939", "#FF9700"],
            data: Products.map(m => m?.vendas),
          },
        ],
        labels: Products.map(m => m?.produto),
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
      },
    };
  },
};
</script>
