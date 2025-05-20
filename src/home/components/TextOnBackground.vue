<script setup lang="ts">
defineProps<{
  text: string
  image: string
}>();
</script>

<template>
     <div class="text-bg" :style="{ backgroundImage: `url(${image})` }">
      <div class="text-bg__container">
        <span class="text-bg__content">
          {{ text }}
        </span>
      </div>
    </div>
</template>

<style lang="scss" scoped>
.text-bg {
  position: relative;
  height: 100%;
  background-size: cover;
  background-position: 0px 40%; 
  border-radius: pxToRem(24px);
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  font-family: "Hedvig Letters Serif";
  color: var(--white);
  font-size: pxToRem(24px);
  overflow: hidden;
  padding: 32px;

  &::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(81.86deg, rgba(17, 0, 28, 0.88) 40%, rgba(17, 0, 28, 0) 100%);
    z-index: 1;
  }

    &__container {
        max-width: pxToRem(220px);
        z-index: 100;
    }
  }
</style>