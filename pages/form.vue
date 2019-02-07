<template>
  <section>
    <div id="app">
      <h1> Keywords -> JSON </h1>
      <JSONForm/>
    </div>
  </section>
</template>

<script>
import JSONForm from '~/components/JSONForm.vue'
import Vue from 'vue'

new Vue({ 
  el: '#app'
})

export default {
  components: {
    JSONForm
  }
}
</script>

<style>
</style>