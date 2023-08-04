<template>
  <AppHeader v-if="windowWidth >= 950"/>
  <MobileHeader v-else/>
  <main>
    <AppAside v-if="windowWidth >= 950"/>
    <AppContent />
  </main>
</template>

<script>
import AppAside from './components/AppAside.vue';
import AppHeader from './components/AppHeader.vue';
import AppContent from './components/AppContent.vue';
import MobileHeader from './components/MobileHeader.vue';


export default {
  name: 'App',
  components: { AppHeader, AppAside, AppContent, MobileHeader },
  data() {
    return {
      windowWidth: window.innerWidth
    }
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener('resize', this.onResize);
    })
  },

  beforeDestroy() { 
    window.removeEventListener('resize', this.onResize); 
  },

  methods: {  
    onResize() {
      this.windowWidth = window.innerWidth
    }
  }
}
</script>

<style lang="scss">
#app {
  padding: 0 100px;
}

main {
  display: flex;
  gap: 36px;
}

@media (max-width: 1200px) {
  #app {
    padding: 0 50px;
  }
}

@media (max-width: 1000px) {
  #app {
    padding: 0 20px;
  }
}

@media (max-width: 940px) {
  #app {
    padding: 0 40px;
  }
}

@media (max-width: 750px) {
  #app {
    padding: 0 25px;
  }
}

@media (max-width: 500px) {
  #app {
    padding: 0 16px;
  }
}
</style>
