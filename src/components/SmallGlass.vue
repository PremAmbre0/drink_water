<template>
  <div class="small-glass-container" :class="{ 'is-selected': isSelected } ">
    250 ml
  </div>
</template>

<script>
export default {
  name: "SmallGlass",
  props: {
      isSelected: {
          required: true,
          type: Boolean,
          default: false
      }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.small-glass-container {

}
</style>
