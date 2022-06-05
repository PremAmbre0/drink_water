<template>
  <div class="large-glass-container">
    <div class="large-glass-container--unfilled" :style="{ height: unfilledPercentage + '%' }">
      <span class="large-glass-container--unfilled-liters">{{ liters }}L</span><span class="large-glass-container--unfilled-remained">  Remained</span>
    </div>
    <div class="large-glass-container--filled" :style="{ height: filledPercent + '%', opacity:opacity}">
      {{ filledPercent + '%' }}
    </div>
  </div>
</template>

<script>
export default {
  name: "LargeGlass",
  data() {
    return {
    }
  },
  computed: {
    filledPercent() {
      return this.value * 12.5;
    },
    unfilledPercentage() {
      return 100 - this.filledPercent
    },
    liters() {
      return 2 - this.value * 0.25
    },
    opacity(){
      if (this.filledPercent){
        return 1
      }
      else{
        return 0
      }
    }
  },
  props: {
    value: {
      required: true,
      type: Number,
      default: 0,
    },

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.large-glass-container {
  margin-bottom: 2rem;
  height: 25rem;
  width: 12rem;
  border: 4px solid $dark-blue-color;
  border-radius: 0 0 3rem 3rem;
  background-color: $light-blue-color;
  overflow: hidden;
  position: relative;

  &--unfilled {
    background-color: #fff;
    transition: height .3s ease ;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    &-liters {
      color: $dark-blue-color;
      font-size: 2rem;
      font-weight: bold;

    }
    &-remained{
      color: $dark-blue-color;
      font-size: 1.2rem;
      
    }
  }

  &--filled {
    width: 100%;
    background-color: $light-blue-color;
    transition: height .3s ease;
    font-size: 3rem;
    font-weight: bold;
    position: absolute;
    bottom: 0;
        color: $dark-blue-color;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
}
</style>
