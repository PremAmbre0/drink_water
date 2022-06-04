<template>
  <div class="large-glass-container"
  :style="{height:filledPercent+'%'}">
    Large
  </div>
</template>

<script>
export default {
  name: "LargeGlass",
  data() {
    return {}
  },
  computed: {
    filledPercent() {
      return this.value * 12.5;
    }
  },
  props: {
    value: {
      required: true,
      type:Number,
      default: 0,
    },

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.large-glass-container {
  margin-bottom: 2rem;  
}
</style>
