<template>
    <div class="container-header">

        <!-- -----------------------------Navbar------------------------ -->
        <div class="header-top">
            <div class="header-top-content">
                <div class="button-responsive">
                    <!-- <button id="menu-button">&#9776;</button> -->
                    <nav>
                        <div class="navbar">
                            <div class="container nav-container">
                                <input class="checkbox" type="checkbox" name="" id="" />
                                <div class="hamburger-lines">
                                    <span class="line line1"></span>
                                    <span class="line line2"></span>
                                    <span class="line line3"></span>
                                </div>

                                <div class="menu-items">
                                    <li><a href="#"> <i class="fa fa-bar-chart"></i></a></li>
                                    <li><a href="#"> <i class="fa fa-user-plus"></i></a></li>
                                    <li><a href="#"> <i class="fa fa-briefcase"></i></a></li>
                                </div>
                            </div>
                        </div>
                    </nav>
                </div>
                <div class="logo-manfing">
                    <img src="../assets/manfing.png" alt="">
                </div>
                <div class="header-top-content-user">
                    <div class="box-toggle">
                        <div>
                            <label class="switch">
                                <input type="checkbox">
                                <span class="slider"></span>
                            </label>
                        </div>
                        <div class="icons-user">
                            <ul>
                                <li>
                                    <i class="fa fa-database" aria-hidden="true"></i>
                                </li>
                                <li>
                                    <i class="fa fa-table" aria-hidden="true"></i>
                                </li>
                                <li>
                                    <i class="fa fa-th-large" aria-hidden="true"></i>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <div class="box-user">
                        <div class="name-user">
                            Estácio Renan
                        </div>
                        <div>
                            <ul class="options-user">
                                <li>
                                    <a href="#" v-on:click.prevent.stop="openDropdownUser()" class="options-user-head">
                                        <i class="fa fa-user-circle fa-1x"></i>
                                    </a>
                                </li>
                            </ul>
                        </div>

                    </div>

                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            isToggled: false
        }
    },
    methods: {
        openDropdownUser() {
            document.getElementById("myDropdownUser").classList.toggle("show");
        },
    }
}
</script>

<style>
.container-header {
    position: fixed;
    width: 100%;
    height: 8vh;
    top: 0;
    display: flex;
    background-color: #fff;
}

.nav {
    width: 200px;
    height: 100%;
    display: inline-block;
    background-color: #fff;
    z-index: 5;
    position: fixed;
}

.nav-mobile {
    display: none;
}

@media only screen and (max-width: 768px) {
    .nav {
        height: auto;
    }

    .nav-mobile {
        display: block;
        cursor: pointer;
        position: absolute;
        right: -3rem;
        text-align: center;
        top: 50%;
        transform: translateY(-50%);
        z-index: 999;
        font-size: 1.4rem;
        padding: 2px 0.5rem 0;
        border-radius: 2px;
    }

    .sidebar-list {
        display: block;
    }

    .nav-mobile i {
        font-size: 30px;
        color: #5CAD8A;
    }
}

.header-top {
    width: 100%;
    height: 100%;
    padding: 0rem;
    background-color: #fff;
    z-index: 1;
    transition: all .2s ease;
    box-shadow: 0px 0px 40px 0px rgba(82, 63, 105, 0.1);
}

.header-top-content {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 100%;
}

.button-responsive {
    width: 33.3%;
    visibility: hidden;
}

.logo-manfing {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 33.3%;
}

.logo-manfing>img {
    width: 50px;
    height: 50px;
}

.header-top-content-user {
    width: 33.3%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.box-user {
    display: flex;
    align-items: center;
}

.box-toggle {
    display: flex;
    align-items: center;
    margin-right: 30px;
}

.icons-user ul {
    list-style-type: none;
    display: flex;
    flex-direction: row;
    margin-left: -30px;
    gap: 10px;
    color: #8F8F8F;
}

.icons-user :where(i) {
    cursor: pointer;
}

.switch {
    font-size: 17px;
    position: relative;
    display: flex;
    width: 30px;
    height: 20px;
}

.switch input {
    opacity: 1;
    width: 0;
    height: 0;
}

.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0px;
    background: #fff;
    transition: .4s;
    border-radius: 30px;
    border: 1px solid #ccc;
}

.slider:before {
    position: absolute;
    content: "";
    height: 1em;
    width: 1em;
    border-radius: 16px;
    left: 1px;
    top: 0;
    bottom: 0;
    background-color: white;
    box-shadow: 0 2px 5px #999999;
    transition: .4s;
}

input:checked+.slider {
    background-color: #000;
    border: 1px solid transparent;
}

input:checked+.slider:before {
    transform: translateX(0.6em);
}

.options-user {
    margin-right: 30px;
    margin-left: -30px;
    list-style: none;
}

.options-user a.options-user-head {
    font-size: 30px;
    border-radius: 4px;
    color: #D6DBDF;
}

.options-user li ul {
    list-style: none;
}

@media only screen and (max-width: 768px) {
    .box-toggle {
        display: none;
    }

    .name-user {
        display: none;
    }

    .button-responsive {
        visibility: visible;
    }
}

.sidebar-list {
    position: fixed;
    top: 12%;
    z-index: 5;
    display: flex;
    flex-direction: column;
    width: 200px;

}

.sidebar-list-item {
    flex: 1;
    justify-content: center;
    align-items: center;
    text-align: center;
    margin: 15px 0;
    position: relative;
}

.sidebar-list-item i {
    color: #fff;
    font-size: 25px;
    display: flex;
    line-height: 1;
    background-color: aqua;
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

/* Menu Hamburguer */

.navbar {
    justify-content: center;
    width: 100%;
    background-color: #fff;

}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 62px;
}

.navbar .menu-items {
    display: flex;
    width: 50% !important;
    background-color: #fff;
    box-shadow: inset 0px 1px 1px #000 !important;
}

.navbar .nav-container li {
    list-style: none;
}

.navbar .nav-container a {
    text-decoration: none;
    color: #0e2431;
    font-weight: 500;
    font-size: 1.2rem;
    padding: 0.7rem;
}

.navbar .nav-container a:hover {
    font-weight: bolder;
}

.nav-container {
    display: block;
    position: relative;
    height: 53px;
}

.nav-container .checkbox {
    position: absolute;
    display: block;
    height: 32px;
    width: 32px;
    top: 20px;
    left: 20px;
    z-index: 5;
    opacity: 0;
    cursor: pointer;
}

.nav-container .hamburger-lines {
    display: block;
    height: 26px;
    width: 32px;
    position: absolute;
    top: 17px;
    left: 20px;
    z-index: 2;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.nav-container .hamburger-lines .line {
    display: block;
    height: 4px;
    width: 100%;
    border-radius: 10px;
    background: #0e2431;
}

.nav-container .hamburger-lines .line1 {
    transform-origin: 0% 0%;
    transition: transform 0.4s ease-in-out;
}

.nav-container .hamburger-lines .line2 {
    transition: transform 0.2s ease-in-out;
}

.nav-container .hamburger-lines .line3 {
    transform-origin: 0% 100%;
    transition: transform 0.4s ease-in-out;
}

.navbar .menu-items {
    padding-top: 120px;
    box-shadow: inset 0 0 2000px rgba(255, 255, 255, .5);
    height: 100vh;
    width: 100%;
    transform: translate(-150%);
    display: flex;
    flex-direction: column;
    margin-left: -40px;
    padding-left: 50px;
    transition: transform 0.5s ease-in-out;
    text-align: center;
}

.navbar .menu-items li {
    margin-bottom: 1.2rem;
    font-size: 1.5rem;
    font-weight: 500;
    
}

.logo {
    position: absolute;
    top: 5px;
    right: 15px;
    font-size: 1.2rem;
    color: #0e2431;
}

.nav-container input[type="checkbox"]:checked~.menu-items {
    transform: translateX(0);
}

.nav-container input[type="checkbox"]:checked~.hamburger-lines .line1 {
    transform: rotate(45deg);
}

.nav-container input[type="checkbox"]:checked~.hamburger-lines .line2 {
    transform: scaleY(0);
}

.nav-container input[type="checkbox"]:checked~.hamburger-lines .line3 {
    transform: rotate(-45deg);
}

.nav-container input[type="checkbox"]:checked~.logo {
    display: none;
}
</style>
