<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->
    
    <!-- <head> -->
      <div class="sections-menu">
        <div class="right-div">
        <span
           class="menu-point"
           v-bind:class="{active: activeSection == index}"
           v-on:click="scrollToSection(index)"
           v-for="(offset, index) in offsets"
           v-bind:key="index">{{menuString[index]}}
        </span>
        </div>
      </div>
    <!-- </head> -->
    <div>

    
    <!-- Nanti tambahkan @scroll="onScroll" untuk pakai event onScroll -->
    <div class="fullpage turunsikit">
      <section class="turunY">
        <h1>Vue.js Fullpage Scroll</h1>
        <p>by <a href="https://webdeasy.de/?referer=cp-NVOEBL" target="_blank">WebDEasy</a></p>
        <img src="http://riadentalcare.com/asset-user/images/dental2.png" alt="Image" class="size-quarter">
      </section>
      <div class="halfpage background blue">

      </div>
    </div>
    
    <section class="fullpage black">
      <h1>Section 2</h1>
      <p>made with <a href="https://vuejs.org/" target="_blank">Vue.js</a></p>
    </section>
    
    <section class="fullpage red">
      <h1>Section 3</h1>
      <p>works on <b>desktop & mobile</b></p>
    </section>
    <section class="fullpage green">
      <h1>Section 4</h1>
      <p>Tutorial <a href="https://webdeasy.de/en/programming-vue-js-fullpage-scroll/?referer=cp-NVOEBL" target="_blank">here</a></p>
    </section>
  </div>
  </div>
</template>

<script>
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "App",
  // el: "#app",
  // components: {
  //   HelloWorld,
  // },
  data: function(){
    return {
    inMove: false,
    activeSection: 0,
    offsets: [],
    menuString: [
      "Home",
      "About",
      "Portofolio",
      "Contact"
    ],
    touchStartY: 0
  };
  },
  methods: {
    // onScroll ({ target: { scrollTop, clientHeight, scrollHeight }}) {
    //   if (scrollTop + clientHeight >= scrollHeight) {
    //     this.moveDown();
    //     console.log('moveDown onScroll Called');
    //   } else {
    //     this.moveUp();
    //     console.log('moveDown onScroll Called');
    //   }
    // },
    calculateSectionOffsets() {
      let sections = document.getElementsByTagName('section');
      let length = sections.length;
      console.log("ini terpanggil kok " + sections.length);
      
      for(let i = 0; i < length; i++) {
        let sectionOffset = sections[i].offsetTop;
        this.offsets.push(sectionOffset);
      }
    },
    // handleMouseWheel: function(e) {
      
    //   if (e.wheelDelta < 30 && !this.inMove) {
    //     this.moveUp();
    //   } else if (e.wheelDelta > 30 && !this.inMove) {
    //     this.moveDown();
    //   }
        
    //   e.preventDefault();
    //   return false;
    // },
    // handleMouseWheelDOM: function(e) {
      
    //   if (e.detail > 0 && !this.inMove) {
    //     this.moveUp();
    //   } else if (e.detail < 0 && !this.inMove) {
    //     this.moveDown();
    //   }
      
    //   return false;
    // },
    // moveDown() {
    //   this.inMove = true;
    //   this.activeSection--;
        
    //   // if(this.activeSection < 0) this.activeSection = this.offsets.length - 1;
    //   if(this.activeSection < 0) this.activeSection = 0;
        
    //   this.scrollToSection(this.activeSection, true);
    //   console.log('moveDown Terpanggil');
    // },
    // moveUp() {
    //   this.inMove = true;
    //   this.activeSection++;
        
    //   // if(this.activeSection > this.offsets.length - 1) this.activeSection = 0;
    //   if(this.activeSection > this.offsets.length - 1) this.activeSection = this.offsets.length-1;
        
    //   this.scrollToSection(this.activeSection, true);
    //   console.log('moveUp Terpanggil');

    // },
    scrollToSection(id, force = false) {
      if(this.inMove && !force) return false;
      
      this.activeSection = id;
      this.inMove = true;
      
      let sections = document.getElementsByTagName('section');
      sections[id].scrollIntoView({behavior: 'smooth'});
      
      setTimeout(() => {
        this.inMove = false;
      }, 400);
      
    },
    // touchStart(e) {
    //   e.preventDefault();
      
    //   this.touchStartY = e.touches[0].clientY;
    // },
    // touchMove(e) {
    //   if(this.inMove) return false;
    //   e.preventDefault();
      
    //   const currentY = e.touches[0].clientY;
      
    //   if(this.touchStartY < currentY) {
    //     this.moveDown();
    //   } else {
    //     this.moveUp();
    //   }
      
    //   this.touchStartY = 0;
    //   return false;
    // }
  },
  // beforeCreate(){
  //   this.calculateSectionOffsets();

  // },
  
  mounted() {
    this.calculateSectionOffsets();
    
  },
  created() {
    // this.calculateSectionOffsets();
    
    // window.addEventListener('scroll', this.onScroll, { passive: false })
    // window.addEventListener('DOMMouseScroll', this.handleMouseWheelDOM);  // Mozilla Firefox
    // window.addEventListener('mousewheel', this.handleMouseWheel, { passive: false }); // Other browsers
    
    // window.addEventListener('touchstart', this.touchStart, { passive: false }); // mobile devices
    // window.addEventListener('touchmove', this.touchMove, { passive: false }); // mobile devices
  },
  // updated() {
  //   this.calculateSectionOffsets();
  
  // },
  destroyed() {
    // window.removeEventListener('scroll', this.onScroll);  // Other browsers
    // window.removeEventListener('mousewheel', this.handleMouseWheel, { passive: false });  // Other browsers
    // window.removeEventListener('DOMMouseScroll', this.handleMouseWheelDOM); // Mozilla Firefox
    
    // window.removeEventListener('touchstart', this.touchStart); // mobile devices
    // window.removeEventListener('touchmove', this.touchMove); // mobile devices
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

body {
  margin: 0;
  color: #FFF;
  font-family: Helvetica, arial, sans-serif;
  /* overflow: hidden; */
}

h2 {
  position: fixed;
}

.size-quarter{
  width: 40%;
}

.background{
    color: #a86895;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -100;
}

.sections-menu {
  /* align-items: center; */

  position: fixed;
  /* left: 50%; */
  /* top: 1rem; */
  width: 100%;
  height: 10%;
  /* overflow: auto; */

  background-color: #FFF;
  /* transform: translateY(10%); */

  /* right: 1rem;
  top: 50%; */
  /* transform: translateY(-50%); */
}
.sections-menu .right-div {
  width: 50%;
  height: 100%;
  float: right;
  /* transform: translateY(20%); */
  /* text-decoration-color: #000; */
  /* background-color: #111; */
}
.sections-menu .right-div .menu-point {
  
  width: 10px;
  height: 10%;
  /* background-color: #FFF; */
  /* top: 50%; */
  display: inline-block;
  margin: 2rem 4rem 2rem 4rem;
  opacity: .6;
  transition: .4s ease all;
  cursor: pointer;
}

.sections-menu .right-div .active {
  height: 100%;

  /* background-color: #000; */
  margin: 2rem 2rem 2rem 2rem;
  opacity: 1;
  /* margin: 2rem; */
  transform: scale(1.5) translateX(-100%);
  transform-origin: center;
}

.fullpage {
  min-height: 200%;
  /* height:100%; */
  width: 100%;
  overflow:auto; 
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.halfpage {
  min-height: 100%;
  /* height:100%; */
  width: 100%;
  overflow:auto; 
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

h1 {
  font-size: 6em;
  margin: 0;
  text-align: center;
  padding: 0 1rem;
}

p {
  font-size: 1em;
}

.fullpage a {
  text-decoration: none;
  font-weight: 600;
  background: rgba(255, 255, 255, 0.3);
  padding: 5px 10px;
  color: #FFF;
  margin-left: 5px;
}

.red {
  background-color: #ab4545;
}

section.black {
  background-color: #000;
}

.fullpage .turunsikit {
  transform:  translateZ(-100px);
}

.fullpage .turunY{
  /* transform: translateY(10%); */
  padding-top: 5%;
  margin-bottom: 15%;
}

.blue {
  background-color: #ffdcf4;
  border-radius: 0px 0px 500px 0px;
  /* border: 2px solid #73AD21; */
  /* padding: 20px;
  width: 200px;
  height: 150px;  */
}

.green {
  background-color: #68c368;
}

h1.black {
  color: #000;
}





@media screen and (max-width: 1200px) {
  h1 {
    font-size: 2.5em;
  }
}
</style>
