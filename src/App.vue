<template>
  <div id="app">
    <img class="logo" :class="{ 'logo-mobile':isMobile }" src="./assets/Logo.png" alt="FLYTA logo">
    <p class="subtitle" :class="{'subtitle-mobile':isMobile}">Available now on iOS!</p>
    <img class="asteroid spin-med spin-rev" v-if="!isMobile" style="width: 200px; top: 250px; left: 500px;" src="./assets/asteroids/asteroid6.svg" alt="asteroid">
    <img class="asteroid spin-med spin-rev" v-if="isMobile" style="width: 100px; top: 270px; left: -5px;" src="./assets/asteroids/asteroid6.svg" alt="asteroid">
    <img class="asteroid spin-slow"  v-if="!isMobile" style="width: 200px; top: 600px; left: 1200px;" src="./assets/asteroids/asteroid8.svg" alt="asteroid">
    <img class="asteroid spin-slow"  v-if="isMobile" style="width: 130px; top: 500px; left: 280px;" src="./assets/asteroids/asteroid8.svg" alt="asteroid">
    <img class="cargo spin-fast" v-if="!isMobile" style="width: 100px;" src="./assets/cargo.svg" alt="cargo">
    <img class="cargo spin-fast" v-if="isMobile" style="width: 50px; top:400; left: 10px;" src="./assets/cargo.svg" alt="cargo">
    <img class="spaceMan" :class="{ 'spaceMan-mobile':isMobile }" src="./assets/spaceMan.svg" alt="spaceman">
    <a  class="appStore" :class="{ 'appStore-mobile':isMobile }" href="https://apps.apple.com/us/app/flyta/id1478797241?ls=1">
      <img   src="./assets/appStore.svg" alt="appStore Logo">
    </a>
    
    
    <iframe  class="video" :class="{ 'video-mobile':isMobile }" width="560" height="315" src="https://www.youtube-nocookie.com/embed/IJun4CwX6rM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    <Support class="support"/>
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
  },
  data(){
    return{
      window: {
        width: 0,
        height: 0
      },
      isMobile: false
    }
  },
  created(){
  // const self = this;
    window.addEventListener('resize', this.handleResize)
    this.handleResize();
  },
  destroyed() {
    window.removeEventListener('resize', this.handleResize)
  },  
  methods:{
    handleResize() {
      this.window.width = window.innerWidth;
      this.window.height = window.innerHeight;
/* eslint-disable no-console */

      if(this.window.width < 600){
        this.isMobile = true;
      }else{
        this.isMobile = false;
      }
    }, 
  },
}
</script>

<style lang="scss">
@import './style.scss';

html{
  z-index: 200;
  height: 100%;
  width: 100%;
  margin: 0;
  background-color: #202020;
  background-size: 350px;
  background-image: url("./assets/stars.svg");
  background-repeat: repeat;
}

a{
  padding-top: 40px;
  margin: 0;
  display: block;
  margin: 0 auto;
  text-align: center;
}

.logo{
  padding-top: 100px;
  display: block;
  margin: 0 auto;
  text-align: center;
  width: 25%;
}
.logo-mobile{
  width: 70%;  
}

.subtitle{
  text-align: center;
  color:white;
  font-family: 'poppins';
  font-size: 150%;
  padding-top: 10px;
}

.spaceMan{
  transform-origin: 50% 52%;
  padding-top: 50px;
  padding-bottom: 50px;
  display: block;
  width: 15%;
  margin: 0 auto;
  animation-name: spin;
  animation-duration: 60s;
  animation-iteration-count: infinite;
  animation-timing-function: linear; 
}
.spaceMan-mobile{
  width: 50%;
}

.appStore{
    img{
      width: 10%;
    }
}

.appStore-mobile{
    img{
      width: 50%;
    }
}

@keyframes spin {
  from {
      transform:rotate(0deg);
  }
  to {
      transform:rotate(360deg);
  }  
}

.spin-fast{
  animation-name: spin;
  animation-duration: 60s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;  
}

.spin-med{
  animation-name: spin;
  animation-duration: 90s;
  animation-iteration-count: infinite;
  animation-timing-function: linear; 
}

.spin-slow{
  animation-name: spin;
  animation-duration: 120s;
  animation-iteration-count: infinite;
  animation-timing-function: linear; 
}

.spin-rev{
  animation-direction: reverse;
}

.cargo{
  position: absolute;
  top: 500px;
  left: 500px;
  z-index: 20000;
  transform-origin: center;
  animation-name: spin;
  animation-duration: 60s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;  
}

.asteroid{
  position: absolute;
  z-index: 100;
  transform-origin: center;

}


.video{
  padding-top: 80px;
  display:block;
  margin: 0 auto;
  width: 25%;
}
.video-mobile{
  width: 100%;
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
