<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import TopBar from './components/TopBar.vue'
</script>

<script>
import Home from './components/HomePage.vue'
import ShipPage from './components/ShipPage.vue'
import NotFound from './components/404.vue'

const routes = {
  '/': Home,
  '/ship': ShipPage,
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = window.location.hash
    })
  }
}
</script>


<template>
  <main class="flex flex-col h-screen">
    <TopBar />
    <!-- <div class="h-full"> -->
      <div class="div-pad grow">
        <ShipPage />
        <!-- <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
            <HelloWorld msg="You did it!" />
            <a href="#/">Home</a> | <a href="#/na"></a> -->
  
      </div>
      <!-- <TheWelcome /> -->
     
      <div class="div-pad grow max-h-80 h-60 bg-bottom-curve bg-cover bg-center">
        <p> This is the bottom half</p>
         <component :is="currentView" />
      </div>
   <!-- </div> -->
  </main>

  
</template>

<style scoped>
main {
  /* min-height: inherit; */
}
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  } 
}*/
</style>
