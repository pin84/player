<template>
  <div id="app">
    <aHeader></aHeader>
    <tab></tab>
    <router-view></router-view>
  </div>
</template>

<script>
import aHeader from './components/header/Header'
import Tab from './components/tab/tab'
export default {
  components: {
    aHeader,
    Tab
  }
}
</script>

<style>
</style>
