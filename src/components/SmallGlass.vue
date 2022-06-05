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
  height: 9.5rem ;
  width: 5rem;
  border: 4px solid $dark-blue-color;
  background-color: #fff;
  font-size:1.8rem;
  text-align:center;
  word-wrap:normal;
  color:$dark-blue-color;
  border-radius:0 0 1.5rem 1.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.2s ease-in;
}
.is-selected{
  background-color: $light-blue-color;

}
</style>
