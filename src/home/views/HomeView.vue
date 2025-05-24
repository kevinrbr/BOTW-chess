<script setup lang="ts">
import TextOnBackgroundVue from '@/home/components/TextOnBackground.vue';
import SignUpForm from '../components/SignUpForm.vue';
import ChessCarousel from '@/home/components/ChessCarousel.vue';
import chess1 from '@/common/assets/chess1.png';
import chess2 from '@/common/assets/chess2.png';

</script>

<template>
  <div class="bento">
    <div class="bento__one"></div>
    <div class="bento__two">
      <SignUpForm />
    </div>
    <div class="bento__three">
      <TextOnBackgroundVue text="Alapine More Than a Club A True Passion for Chess" :image="chess1" />
    </div>
    <div class="bento__four">
      <TextOnBackgroundVue text="Step into the World of Alapine Chess Club" :image="chess2" />
    </div>
    <div class="bento__five"></div>
    <div class="bento__six">
      <ChessCarousel />
    </div>
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
