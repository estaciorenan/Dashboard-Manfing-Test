<template>
    <div class="container-sidebar">
        <!-- -----------------------------Button Toggle------------------------ -->
        <!-- <div class="nav">
            <div class="nav-mobile">
                <i class="fa fa-bars" v-on:click="openMenuMobile()"></i>
            </div>
        </div> -->

        <!-- -----------------------------Sidebar------------------------ -->
        <div class="sidebar-list" id="sidebar">
            <div class="sidebar-list-item">
                <div class="box-icon">
                    <i class="fa fa-bar-chart"></i>
                </div>
                Dashboard
            </div>
            <div class="sidebar-list-item">
                <div class="box-icon">
                    <i class="fa fa-user-plus"></i>
                </div>
                Clientes Potenciais
            </div>
            <div class="sidebar-list-item">
                <div class="box-icon">
                    <i class="fa fa-briefcase"></i>
                </div>
                Negocios
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Sidebar',
    data() {
        return {

        }
    },
    methods: {
        openMenuMobile() {
            document.getElementById("sidebar-list").classList.toggle("showSidebar");
        }
    }
}
</script>

<style>
@media only screen and (max-width: 768px) {
    .container-sidebar {
        width: 0px !important;
    }
}

.container-sidebar {
    display: inline-block;
    width: 15%;
    height: 100%;
    background-color: #fff !important;
}

.nav {
    visibility: hidden;
    width: 200px;
    height: 100%;
    display: inline-block;
    z-index: 5;
    position: fixed;
}

.nav-mobile {
    display: none;
}


.sidebar-list {
    position: fixed;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    width: 200px;
    margin-left: 10px;
    font-family: Roboto;
    font-size: 12px;
}

.sidebar-list-item {
    display: flex;
    justify-content: left !important;
    margin: 15px 0;
    position: relative;
}

.box-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 30px;
    height: 30px;
    margin-right: 8px;
    background-color: #0D84AE !important;
    border-radius: 3px;
    color: #fff;
    line-height: 1;
    cursor: pointer;
}

.sidebar-list-item i {
    background-color: #0D84AE !important;
    font-size: 14px !important;

}

@media only screen and (max-width: 768px) {
    .sidebar-list {
        left: -100%;
        transition: all 300ms ease-in-out;
        background-color: #fff;
        height: 100%;
    }

    .showSidebar {
        left: 0%;
        top: 0;
    }
}
</style>
