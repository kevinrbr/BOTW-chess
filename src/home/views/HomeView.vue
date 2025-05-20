<script setup lang="ts">
import TextOnBackgroundVue from '@/home/components/TextOnBackground.vue';

</script>

<template>
  <div class="bento">
    <div class="bento__one"></div>
    <div class="bento__two"></div>
    <div class="bento__three">
     <TextOnBackgroundVue 
        text="Alapine More Than a Club A True Passion for Chess"
        image="src/common/assets/chess1.png"  
     />
    </div>
    <div class="bento__four">
      <TextOnBackgroundVue 
        text="Step into the World of Alapine Chess Club"
        image="src/common/assets/chess2.png"  
      />
    </div>
    <div class="bento__five"></div>
    <div class="bento__six"></div>
  </div>
</template>

<style scoped lang="scss">
.bento {
  display: grid;
  height: 100dvh;
  gap: pxToRem(24px);
  padding: 24px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(4, 1fr);
  grid-template-areas:
    'one one one two two'
    'one one one two two'
    'three three five six six'
    'four four five six six';

  &__one {
    border-radius: pxToRem(24px);
    grid-area: one;
    background-image: url('@/common/assets/club.png');
    background-size: cover;
  }

  &__two {
    border-radius: pxToRem(24px);
    grid-area: two;
    background-color: green;
  }

  &__three {
    grid-area: three;
  }

  &__four {
    border-radius: pxToRem(24px);
    grid-area: four;
    background-color: crimson;
  }

  &__five {
    border-radius: pxToRem(24px);
    grid-area: five;
    background-image: url('@/common/assets/goat.png');
    background-size: cover;
  }
  
  &__six {
    border-radius: pxToRem(24px);
    grid-area: six;
    background-color: rgb(73, 104, 243);
  }
}
</style>