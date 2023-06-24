<template>
    <div class="dashboard">

        <div class="title">
            <h3>Histórico</h3>
        </div>
        <hr />

        <div class="cards">
            <div class="card-sales">
                <div class="sales">
                    <div>
                        <DoughnutChart />
                    </div>

                </div>
            </div>
            <div class="card-products">
                <div class="products">

                    <div class="products-title">
                        <div style="width: 50%;">Produtos</div>
                        <div style="display: flex; width: 50%;">
                            <div style=" width: 50%; text-align: center;">
                                Vendas
                            </div>
                            <div style=" width: 50%; text-align: center;">
                                Porcentagem
                            </div>
                        </div>
                    </div>

                    <div class="for-products" v-for="produtos in product">
                        <div style=" width: 50%;">
                            {{ produtos?.produto }}
                        </div>
                        <div style="display: flex; width: 50%;">
                            <div style="width: 50%; text-align: center;">
                                {{ produtos?.vendas }}
                            </div>
                            <div style="width: 50%; text-align: center;">
                                {{ produtos?.porcentagem }}%
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>

        <div class="cards">
            <div class="card-total-sales">
                <div class="total-sales">
                    <LineChart />
                </div>
            </div>
        </div>

    </div>
</template>

<script>
import DoughnutChart from './Doughnut.vue';
import LineChart from './LineChart.vue';
import axios from 'axios';
import dataProduto from '../data/topProduto.json';

export default {
    name: 'Dashboard',
    components: {
        DoughnutChart,
        LineChart,
    },
    data() {
        return {
            product: dataProduto,
        }
    }
}
</script>

<style>
@media only screen and (max-width: 768px) {
    .dashboard {
        width: 100%;
    }

    .cards {
        flex-direction: column;
    }

    .card-sales {
        width: 100% !important;
    }
    .sales{
        margin: 12px 0px !important;
    }
    .card-products {
        width: 100% !important;
    }
    .products{
        margin: 12px 0px !important;
        font-size: 10px !important;
    }
    .total-sales{
        margin-bottom: 50px !important;
    }

}

.dashboard {
    width: 95%;
    display: inline-block;
    flex-direction: column;
    margin: auto;
    margin-top: -2px;
}

.title {
    margin: 30px 0px 10px 0px;
}

hr {
    border: 1px solid #F2F4F4;
}

.cards {
    display: flex;
    flex-wrap: wrap;
}

.card-sales {
    width: 50%;
}

.sales {
    background-color: #fff;
    margin: 12px 12px 12px 0px;
    height: 300px;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
    border-radius: 5px;
    padding: 10px;
}

.card-products {
    width: 50%;
}

.products {
    background-color: #fff;
    margin: 12px 0px 12px 12px;
    height: 300px;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
    border-radius: 5px;
    font-size: 12px;
    padding: 10px 5px
}

.products-title {
    display: flex;
    width: 95%;
    font-weight: bolder;
    border-top: 1px solid #F2F4F4;
    border-bottom: 1px solid #F2F4F4;
    margin-top: 5px;
    margin: 0px 10px;
    padding: 2px 0px;
}

.for-products {
    display: flex;
    flex-direction: row;
    width: 95%;
    border-bottom: 1px solid #F2F4F4;
    padding: 2px 0px;
    margin: 0px 10px;
}

.card-total-sales {
    width: 100%;
}

.total-sales {
    background-color: #fff;
    margin: 12px 0px;
    height: 300px;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
    border-radius: 5px;
    padding: 10px;
}
</style>
