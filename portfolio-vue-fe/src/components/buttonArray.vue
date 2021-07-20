<template>
    <div>
      <button v-for='data in buttonData' :key="data.name" @click='$emit("buttonEvent",data.event)' class='customButton col-6'>{{data.name}}</button>
    </div>
</template>

<script>

export default {
  name: 'buttonArray',
  components: {
  },
  props: {
    'buttonData':[],
  },
  data: function () {
    return {
      loaded: false,
      startSlide: false,
    }
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.customButton {
  width:95%;
  text-align: center;
  color: #FFFFFF;
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  background-color:transparent;
  border: 1px solid #FEA82F;
  border-radius:10px;
}

.customButton:hover {
  color: #FFFFFF;
  transition:0.3s;
  background-color:#FEA82F;
  -webkit-box-shadow: 3px 4px 6px -4px #000000; 
  box-shadow: 3px 4px 6px -4px #000000;
}
</style>
