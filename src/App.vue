<template>
  <div id="app" class="drink-water-wrapper">
    <h1 class="heading heading-primary ">Drink water</h1>
    <h2 class="heading heading-secondary ">Goal : 2 Liters</h2>
    <large-glass :value="selectedIndex"></large-glass>
    <div class="text">Select how many glasse of water have you drank</div>
    <div class="small-glasses-wrapper">
      <small-glass v-for="i in 8" :key="i" :index="i" :isSelected="selectedIndex >= i"
        @click.native="handleSmallGlassClick(i)">
      </small-glass>
    </div>
  </div>
</template>

<script>

import LargeGlass from '@/components/LargeGlass.vue'
import SmallGlass from '@/components/SmallGlass.vue'

export default {
  name: "App",
  components: {
    LargeGlass,
    SmallGlass
  },
  data: () => {
    return {
      selectedIndex: 0,
    }
  },
  methods: {
    handleSmallGlassClick(index) {
      // console.log(index);
      // this.selectedIndex = index;
      // if clicked on filled glass on in less than i will be filled all more than i and i will un filled
      if (this.selectedIndex == index) {
        this.selectedIndex -= 1;
      }
      else {
        this.selectedIndex = index;
      }
    }
  },
};
</script>

<style lang="scss">

.heading{
  color:#fff;
  margin: 1rem 0;
  &-primary{
    font-size: 3.2rem;
  }
  &-secondary{
    font-size:1.8rem
}
}
.drink-water-wrapper {
  display: flex;
  height: 130vh;
  width: 100vw;
  align-items: center;
  justify-content: center;
  flex-direction: column;

  .small-glasses-wrapper {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }
}
.text {
    color: #fff;
    font-size: 1.8rem;
    letter-spacing: 0.05rem;
    margin: 1rem;
}


</style>
