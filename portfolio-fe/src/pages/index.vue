<template>
  <div>
    index loaded
    <typewriter
  :speed="200"
  :full-erase="true"
  :interval="300"
  :words='["Awesome!","Amazing!"]'>
  Vue Typewriter is
</typewriter>
    <VueTyper
  :text='["Arya Stark","Jon Snow","Daenerys Targaryen","Melisandre","Tyrion Lannister"]'
  :repeat='Infinity'
  :shuffle='false'
  initial-action='typing'
  :pre-type-delay='70'
  :type-delay='70'
  :pre-erase-delay='2000'
  :erase-delay='250'
  erase-style='select-all'
  :erase-on-complete='false'
  caret-animation='blink'
  />
  </div>
</template>

<script>

import VueTyper from 'vue-typer';
import Typewriter from 'vue-typewriter'
export default {
  name: 'index',
  components: {
    VueTyper,
    Typewriter,
  },
  props: {},
  data: function () {
    return {
    welcomeText: [`Hi! I'm Alex`],
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
