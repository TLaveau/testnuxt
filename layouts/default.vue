<template>
  <div>
    <top-header/>
    <main>
      <nuxt/>
    </main>
    <bottom-footer/>
  </div>
</template>

<script>
import Vue from 'vue'
import TopHeader from '~/components/TopHeader.vue'
import BottomFooter from '~/components/BottomFooter.vue'

new Vue({ 
  el: '#app'
})

export default {
  components: {
    TopHeader,
    BottomFooter
  }
}
</script>

<style>
html{
  font-family: Quicksand;
}
</style>