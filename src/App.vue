<template>
  <div id="app">
    <top-bar></top-bar>
    <top-header></top-header>
  </div>
</template>

<script>
import TopBar from './components/TopBar'
import TopHeader from './components/TopHeader'

export default {
  components: {
    'top-bar': TopBar,
    'top-header': TopHeader
  }
}
</script>

<style>
@import './assets/css/base.css';
</style>
