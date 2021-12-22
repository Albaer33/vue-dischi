<template>
  <div id="app">

    <Header/>
    <Albumlist />

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Albumlist from './components/Albumlist.vue';

export default {
  name: 'App',
  components: {
    Header,
    Albumlist,
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
</style>
