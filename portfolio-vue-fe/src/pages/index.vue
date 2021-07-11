<template>
  <div class="bg-grey">
    <VueTyper
    :text='welcomeText'
    initial-action='typing'
    :pre-type-delay='70'
    :type-delay='70'
    :erase-on-complete='false'
    caret-animation='blink'
    />
  </div>
</template>

<script>

import { VueTyper } from 'vue-typer';
export default {
  name: 'index',
  components: {
    VueTyper,
  },
  props: {},
  data: function () {
    return {
        welcomeText:`Hi! I'm Alex`,
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bg-grey {
    background: #292F36;
}

.bg-white {
    background: #FFFFFF;
}
</style>
