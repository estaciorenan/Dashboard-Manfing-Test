<template>
    <LineChartGenerator :chart-options="chartOptions" :chart-data="chartData" :chart-id="chartId"
        :dataset-id-key="datasetIdKey" :plugins="plugins" :css-classes="cssClasses" :styles="styles" :width="width"
        :height="height" class="h-30rem" />
</template>
  
<script>
import { Line as LineChartGenerator } from 'vue-chartjs/legacy'
import fatura from '../data/faturamentoAnual.json';


import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    LineElement,
    LinearScale,
    CategoryScale,
    PointElement
} from 'chart.js'

ChartJS.register(
    Title,
    Tooltip,
    Legend,
    LineElement,
    LinearScale,
    CategoryScale,
    PointElement
)


export default {
    name: 'LineChart',
    components: {
        LineChartGenerator
    },
    props: {
        chartId: {
            type: String,
            default: 'line-chart'
        },
        datasetIdKey: {
            type: String,
            default: 'label'
        },
        width: {
            type: Number,
            default: 400
        },
        height: {
            type: Number,
            default: 300
        },
        cssClasses: {
            default: '',
            type: String
        },
        styles: {
            type: Object,
            default: () => { }
        },
        plugins: {
            type: Array,
            default: () => []
        }
    },
    data() {
        return {
            chartData: {
                labels: fatura.map(m => new Date( m?.data).toLocaleString('default', { month: 'long' })),
                datasets: [
                    {
                        label: 'Total de Vendas - Últimos 12 meses',
                        backgroundColor: '#5C5CFA',
                        borderColor: '#5C5CFA',
                        fill: false,
                        data: fatura.map(m => m?.faturamentoMes.toLocaleString('pt-br',{style: 'currency', currency: 'BRL'})),
                        tension: 0.4,
                    }
                ]
            },
            chartOptions: {
                responsive: true,
                maintainAspectRatio: false
            }
        }
    }
}
</script>
  