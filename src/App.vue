<template>
  <div id="app">
    <top-bar></top-bar>
    <top-header></top-header>
    <top-banner></top-banner>
  </div>
</template>

<script>
import TopBar from './components/TopBar'
import TopHeader from './components/TopHeader'
import TopBanner from './components/TopBanner'

export default {
  components: {
    'top-bar': TopBar,
    'top-header': TopHeader,
    'top-banner': TopBanner
  }
}
</script>

<style>
@import './assets/css/base.css';
</style>
