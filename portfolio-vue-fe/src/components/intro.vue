<template>
    <div v-if="loaded" class="centering">
        <VueTyper
        :text='welcomeText[0]'
        initial-action='typing'
        :pre-type-delay='0'
        :type-delay='300'
        :erase-on-complete='false'
        :repeat='0'
        caret-animation='blink'
        />

        <VueTyper
        :text='welcomeText[1]'
        initial-action='typing'
        :pre-type-delay='3000'
        :type-delay='90'
        :erase-on-complete='false'
        :repeat='0'
        caret-animation='blink'
        @completed='$emit("completedIntro")'
        />
    </div>
</template>

<script>

import { VueTyper } from 'vue-typer';
export default {
  name: 'intro',
  components: {
    VueTyper
  },
  props: {},
  data: function () {
    return {
      welcomeText:[`Hi!`,` I'm Alex`],
      loaded:false,
    }
  },
  mounted: function() {
    setTimeout(()=>this.loaded = true,500)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.centering {
    position: absolute;
    transform: translate(-50%, -50%);
    animation: 0.5s ease-in slideFromBottom;
    left: 50%;
    top: 50%;
}

.vue-typer {
  font-size:50px;
  .custom.char {
    color: #FFFFFF;
  }
}

@keyframes slideFromBottom {
  0% {
    transform: translate(-50%, 100%);
    opacity: 0;
  }
  100% {
    transform: translate(-50%, -50%);
    opacity: 1;
  }
}
</style>
