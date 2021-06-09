<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
@import './style/general';
@import '~@fontsource/roboto/index.css';
@import '~@fontsource/roboto/700.css';
@import '~@fontsource/roboto/500.css';
</style>
 
 
