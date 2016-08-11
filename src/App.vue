<template>
  <div id="app">
    <top-bar></top-bar>
  </div>
</template>

<script>
import TopBar from './components/TopBar'

export default {
  components: {
    'top-bar': TopBar
  }
}
</script>

<style>
@import './assets/css/base.css';
</style>
