<template>
  <div id="app">
    <top-bar></top-bar>
    <top-header></top-header>
    <top-banner></top-banner>
    <top-sub></top-sub>
  </div>
</template>

<script>
import TopBar from './components/TopBar'
import TopHeader from './components/TopHeader'
import TopBanner from './components/TopBanner'
import TopSub from './components/TopSub'

export default {
  components: {
    'top-bar': TopBar,
    'top-header': TopHeader,
    'top-banner': TopBanner,
    'top-sub': TopSub
  }
}
</script>

<style>
@import './assets/css/base.css';
</style>
