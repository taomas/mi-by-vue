<template>
  <div id="app">
    <top-bar></top-bar>
    <top-header></top-header>
    <top-banner></top-banner>
    <top-sub></top-sub>
    <goods></goods>
  </div>
</template>

<script>
import TopBar from './components/TopBar'
import TopHeader from './components/TopHeader'
import TopBanner from './components/TopBanner'
import TopSub from './components/TopSub'
import Goods from './components/Goods'

export default {
  components: {
    'top-bar': TopBar,
    'top-header': TopHeader,
    'top-banner': TopBanner,
    'top-sub': TopSub,
    'goods': Goods
  }
}
</script>

<style>
@import './assets/css/base.css';
</style>
