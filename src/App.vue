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
    
    <div class="body" :class="{ 'body-mobile':isMobile }">
      <div class="body-container">
        <div id="text">
          <p>Flyta is an incredibly difficult game with simple controls.</p>
          <p>Help a lost spaceman get back home by traveling through 40 difficult levels, each with their own unique challenges to overcome.</p>
          <br>
          <div class="featured">
            <p class="bold">Featuring:</p>
            <p>- One-touch controls</p>
            <p>- 40 Unique levels</p>
            <p>- Difficult gameplay</p>
            <p>- Optional collectables</p>
            <p>- Original soundtrack</p>
          </div>

        </div>
        <div class="video">
          <iframe width="315" height="560" src="https://www.youtube-nocookie.com/embed/IJun4CwX6rM"></iframe>
        </div>
      </div>
    </div>
    <div class="screenshots">
      <img src="./assets/screenshots/ipad_1.png" alt="FLYTA game screenshot">
      <img src="./assets/screenshots/ipad_2.png" alt="FLYTA game screenshot">
      <img src="./assets/screenshots/ipad_3.png" alt="FLYTA game screenshot">
      <img src="./assets/screenshots/ipad_4.png" alt="FLYTA game screenshot">
        <img src="./assets/screenshots/ipad_5.png" alt="FLYTA game screenshot">
    </div>

    <Support class="support" :class="{ 'support-mobile':isMobile }"/>
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

.body{
  margin: 0 auto;
  padding: 30px;
  margin-top: 100px;
  border-radius: 2%;
  width: 50%;
  background-color: $light;
  color:$dark;
  font-family: 'poppins';
  .body-container{
    display:flex;
  }
  .text{
    text-align: left;
    .featured{
      margin-left: 50px;
    }
  }
  .bold{
    font-family: 'optician-sans';
    color: $primary;
    font-size: 40px;
    margin-bottom: 0;
  }
  .video{
  width: 315px;
  height: 560px;
  iframe{
    border: none;
    border-radius: 2%;
    }
  }
}

.body-mobile{
  margin: 0 auto;
  padding: 10px;
  margin-top: 100px;
  border-radius: 1%;
  width: 90%;
  background-color: $light;
  color:$dark;
  font-family: 'poppins';
  .body-container{
    display:flex;
    flex-direction: column;
  }
  .text{
    text-align: left;
    .featured{
      margin-left: 0px;
    }
  }
  .bold{
    font-family: 'optician-sans';
    color: $primary;
    font-size: 40px;
    margin-bottom: 0;
  }
  .video{
  width: 315px;
  height: 560px;
  iframe{
    border: none;
    border-radius: 2%;
    }
  }
}

.screenshots{
  margin: 0 auto;
  margin-top: 80px;
  justify-content: center;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  img{
    padding: 5px;
    width: 200px;
    height: 267px;
    border-radius: 5%;
  }
} 

#app {
  height: 100%;
  width: 100%;
}

.support{
  height: 100%;
  border-radius: 0%;
  width: 50%;
}
.support-mobile{
   width: 90%; 
}
.footer {
  margin-top: 100px;
  padding-top: 7px;
   padding-bottom: 7px;
  font-family: 'optician-sans';
  width: 100%;
  color: white;
  background-color: $dark;
  text-align: left;

  p{
    color: $primary;
    padding-left: 10%;
  }
}

</style>
