<template>
  <div class="container-fluid">
    <introJumbo @completedIntro="completedIntro()"/>
  </div>
</template>

<script>

import introJumbo from '@/components/introJumbo';
export default {
  name: 'index',
  components: {
    introJumbo
  },
  props: {},
  data: function () {
    return {
      loaded: false,
    }
  },
  methods: {
    completedIntro: function() {
      this.loaded = true;
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

.slideFromLeft {
  position: relative;
  animation: 0.5s ease-out slideInLeftAnimation;
}

@keyframes slideInLeftAnimation {
  0% {
    transform: translate(-50%, 0%);
    opacity: 0;
  }
  100% {
    transform: translate(0%, 0%);
    opacity: 1;
  }
}

.op-0 {
  opacity: 0;
}

</style>
