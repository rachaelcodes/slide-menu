<template>
<div class="navigation-wrapper">
    <div class="navigation-bar">
        <button class="menu-toggle" type="button" v-on:click="openTray">
            Menu
        </button>
        <div class="navigation-bar-links" v-for="part in parts" :key="part.text" >
            <a :href="part.link">{{part.text}}</a>
        </div>
    <img src="drop.png" alt="drop" v-if="tray==='closed'">
    </div>
    <!-- maybe add another media query here to save loading? -->
    <div class="navigation-panel" :class="tray">
        <div class="navigation-row" v-on:click="closeTray">
            <img src="drop.png" alt="drop"> &nbsp; CLOSE
        </div>
        <div class="navigation-row" v-for="part in parts" :key="part.text" >
            <a :href="part.link">{{part.text}}</a>
        </div>
        
    </div>
</div>
</template>

<script>
import Media from 'vue-media'
export default {
    components: {
        Media
    },
    data: function () {
      return {
          tray: 'closed',
          parts: [
              {link: '#jellyfish', text: 'Jellyfish'},
              {link: '#ray', text: 'Ray'},
              {link: '#shark', text: 'Shark'},
              {link: '#yellow', text: 'Yellow'},
              {link: '#zebra', text: 'Zebra'},
            ]
        }
    },
    methods: {
      openTray: function() {
          this.tray='opened';
      },
      closeTray: function() {
          this.tray='closed';
      },
    }
}
</script>

<style>
.navigation-bar {
    position: relative;
    height: 3rem;
    text-align: right;
}
.navigation-bar-links {
    padding: 1rem;
    display: none;
}
.menu-toggle {
    display: inline-block;
    position: absolute;
    left: 1rem;
    top: 1rem;
}
.navigation-panel {
    position: fixed;
    top: 0;
    left: -10rem;
    width: 10rem;
    height: 100%;
    z-index: 10;
    overflow-x: hidden;
    overflow-y: auto;
    background-color:black;
    color: white;
    transition: left .2s ease;

}
.opened {
    left: 0;
}

.navigation-row {
    width: 100%;
    border-top: 1px midnightblue solid;
}


@media (min-width: 600px) {
  .navigation-bar-links {
    display: inline-block
  }
  .menu-toggle {
      display: none
  }
}
</style>
