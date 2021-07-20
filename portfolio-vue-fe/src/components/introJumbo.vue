<template>
    <div class="row bg-grey d-flex align-items-center">
      <div class="col-5 pl-5">
        <div class="textBlock">
          <intro @completedIntro="
          completedIntro()
          $emit('completedIntro')"/>
          <div :class="startSlide ? 'slideFromLeft' : 'op-0'" v-if="loaded">
            I’m a fullstack software engineer,
            And... Yea...
            Welcome to my website,
            hopefully you can know a thing or two
            about me.
          </div>
          <buttonArray :class="startSlide ? 'slideFromLeft' : 'op-0'" v-if="loaded" :buttonData='buttonData' @buttonEvent='handleButtonEvent($event)'/>
        </div>
      </div>
    </div>
</template>

<script>

import intro from '@/components/intro';
import buttonArray from '@/components/buttonArray';
export default {
  name: 'introJumbo',
  components: {
    intro,
    buttonArray
  },
  props: {},
  data: function () {
    return {
      loaded: false,
      startSlide: false,
      buttonData: [
        {name:'Internship',event:'scrollToInternship'},
        {name:'Projects',event:'scrollToProjects'},
        {name:'Education',event:'scrollToEducation'},
        {name:'Contact',event:'scrollToContact'},
      ],
    }
  },
  methods: {
    completedIntro: function() {
      this.loaded = true;
      setTimeout(()=>this.startSlide = true,1100)
    },
    handleButtonEvent: function(e) {
      console.log(e)
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.op-0 {
  opacity: 0;
}
</style>
