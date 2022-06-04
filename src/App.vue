<template>
  <div id="app" class="drink-water-wrapper">
    <large-glass
    :value="selectedIndex"
    ></large-glass>
    <div class="small-glasses-wrapper">
      <small-glass v-for="i in 8" 
      :key="i" 
      :index="i" 
      :isSelected="selectedIndex >= i"
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
      console.log(index);
      // this.selectedIndex = index;
      // if clicked on filled glass on in less than i will be filled all more than i and i will un filled
      if(this.selectedIndex==index) {
        this.selectedIndex-=1;
      }
      else{
        this.selectedIndex = index;
      }
    }  
  },
};
</script>

<style lang="scss">
body {
  padding: 0;
  margin: 0;
}

.drink-water-wrapper {
  display: flex;
  height: 100vh;
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
</style>
