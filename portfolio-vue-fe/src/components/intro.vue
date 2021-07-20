<template>
    <div v-if="loaded" :class="className">
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
        @completed='completedTyping'
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
      className:'centering',
    }
  },
  mounted: function() {
    setTimeout(()=>this.loaded = true,500)
  },
  methods: {
    completedTyping: function() {
      setTimeout(()=>this.className = 'typedPositioning',500)
      setTimeout(()=>this.className = 'endPosition',1500)
      setTimeout(()=>this.$emit("completedIntro"),500)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.centering {
    position: fixed;
    transform: translate(-50%, -50%);
    animation: 0.5s ease-out slideFromBottom;
    left: 50%;
    top: 50%;
}

.typedPositioning {
  position: fixed;
  transform: translate(-50%, -100%);
  animation: 1s ease-out slideAndClear;
  left: 50%;
  top: 50%;
  opacity: 0;
}

.endPosition {
  position: relative;
  animation: 0.5s ease-out slideIn;
}

.vue-typer {
  font-size:50px;
  .custom.char {
    color: #FFFFFF;
    font-family: 'Orbitron', sans-serif;
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

@keyframes slideAndClear {
  0% {
    transform: translate(-50%, -50%);
    opacity: 1;
  }
  100% {
    transform: translate(-50%, -100%);
    opacity: 0;
  }
}

@keyframes slideIn {
  0% {
    transform: translate(-50%, 0%);
    opacity: 0;
  }
  100% {
    transform: translate(0%, 0%);
    opacity: 1;
  }
}
</style>
