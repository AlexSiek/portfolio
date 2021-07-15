<template>
  <div class="bg-grey">
    <div class="textBlock">
      <intro @completedIntro='completedIntro()'/>
      
    </div>
  </div>
</template>

<script>

import intro from '@/components/intro';
export default {
  name: 'index',
  components: {
    intro
  },
  props: {},
  data: function () {
    return {
    }
  },
  methods: {
    completedIntro: function() {
      console.log('completed')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.bg-grey {
  background: #292F36;
  min-width:100vw;
  min-height:100vh;
}

.bg-white {
  background: #FFFFFF;
  min-width:100vw;
  min-height:100vh;
}
</style>
