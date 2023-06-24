<template>
  <div id="app">
    <Header></Header>
    <div class="section">
      <Sidebar></Sidebar>
      <div class="main-content">
        <router-view />
      </div>
    </div>
    <Footer></Footer>

  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue';
import Header from './components/Header';
import Footer from './components/Footer';

export default {
  components: {
    Header, Footer, Sidebar
  }
}
</script>

<style>
@font-face {
  font-family: "Nexa";
  src: local("Nexa"),
    url(./fonts/Nexa-ExtraLight.ttf) format("truetype");
}

#app {
  overflow: hidden;
  font-family: "Nexa", Helvetica, Arial;
}

.section {
  display: flex;
  width: 100%;
  min-height: 95vh;
}

.main-content {
  margin-top: 45px;
  display: flex;
  width: 90%;
  z-index: -1;
  background-color: #F8F9F9;
}

@media only screen and (max-width: 768px) {
  .main-content {
    width: 100%;
    margin-left: 0;
  }
}</style>
