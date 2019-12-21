<template>
  <div id="app">
    <img class="logo" src="./assets/logo.png" alt="">
    <a  href="https://apps.apple.com/us/app/flyta/id1478797241?ls=1">
      <img  class="appStore" src="./assets/appStore.svg" alt="">
    </a>
    <iframe class="video" width="375" height="315" src="https://www.youtube.com/embed/IJun4CwX6rM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    <Support class="main"/>
    <div class="footer">
      <p>2019 Dylan Dougherty</p>

    </div>
  </div>
</template>

<script>
import Support from './components/support.vue';

export default {
  name: 'app',
  components: {
    Support,
  }
}
</script>

<style lang="scss">
@import './style.scss';

html{
  height: 100%;
  width: 100%;
  margin: 0;
  background: #202020;
}


.appStore{
    width: 35%;
}

.video{
  padding-top: 80px;
  display:block;
  margin: 0 auto;

}

a{
  padding-top: 40px;
  margin: 0;
  display: block;
  margin: 0 auto;
  text-align: center;
}


.app{
  width: 100%;
}

.logo{
  padding-top: 100px;
  display: block;
  margin: 0 auto;
  text-align: center;
  width: 70%;
}



#app {
  height: 100%;
  width: 100%;
}

.Support{
  height: 100%;
  height: 100%;
  width: 100%;

}
.footer {
  padding-top: 100px;
  font-family: 'optician-sans';
  width: 100%;
  color: white;
  text-align: left;

  p{
    color: $primary;
    padding-left: 10%;
  }
}

</style>
