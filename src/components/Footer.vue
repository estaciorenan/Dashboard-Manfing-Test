<template>
    <footer>
        <div class="footer-content">
            <div class="footer-manfing">
                <p>
                    2023 Manfing - feito com <i class="fa fa-heart" aria-hidden="true"></i> e muito <i class="fa fa-coffee"
                        aria-hidden="true"></i> no Velho Oeste Paranaense.
                </p>
            </div>
            <div class="footer-business">
                <p>
                    <i class="fa fa-building" aria-hidden="true"></i> Empresa Usinagem - 3edb76bc900028
                </p>
            </div>

        </div>
    </footer>
</template>

<script>
export default {
    name: "Footer",
    data() {
        return {

        }
    }
}
</script>

<style>
footer {
    position: fixed;
    width: 100%;
    background-color: #fff;
    text-align: center;
    height: 5vh;
    bottom: 0;
    font-size: 12px;
    font-weight: 600;
    color: #808B96;
    box-shadow: 0px 0px 40px 0px rgba(82, 63, 105, 0.1);
}

footer .footer-content {
    display: flex;
    width: 100%;
    height: 100%;
    justify-content: space-between;
    align-items: center;
    line-height: 1;
}

.footer-manfing {
    margin-left: 20px;
}

.footer-business {
    margin-right: 20px;
}

@media only screen and (max-width: 768px) {
    .footer-content {
        flex-direction: column;
        font-size: 10px;
        padding-bottom: 5px;
    }

    .footer-manfing{
        display: none;
    }


}
</style>
