<script setup lang="ts">
import { ref, computed } from 'vue'
import king from '@/common/assets/king.png'
import queen from '@/common/assets/queen.png'
import rook from '@/common/assets/rook.png'
import bishop from '@/common/assets/bishop.png'
import knight from '@/common/assets/knight.png'
import pawn from '@/common/assets/pawn.png'
import bg from '@/common/assets/carousel-bg.png'

const currentIndex = ref(0)

const slides = [
  {
    title: 'THE KING',
    text: 'The king is the most important piece. It moves one square in any direction. The goal is to protect your king and avoid checkmate. The king can also castle with a rook to stay safe.',
    image: king,
  },
  {
    title: 'THE QUEEN',
    text: 'The queen is the strongest piece. It can move any number of squares in all directions—straight or diagonal—making it very powerful for attack and defense.',
    image: queen,
  },
  {
    title: 'THE ROOK',
    text: 'The rook moves any number of squares horizontally or vertically. It controls entire rows and columns and is important for castling with the king.',
    image: rook,
  },
  {
    title: 'THE BISHOP',
    text: 'The bishop moves diagonally any number of squares. Each bishop stays on the same color square throughout the game, controlling key diagonal lines.',
    image: bishop,
  },
  {
    title: 'THE KNIGHT',
    text: 'The knight moves in an "L" shape: two squares in one direction and then one square sideways. It’s the only piece that can jump over others.',
    image: knight,
  },
  {
    title: 'THE PAWN',
    text: 'Pawns move forward one square, but two squares on their first move. They capture diagonally. When a pawn reaches the other side, it can be promoted to any other piece, usually a queen.',
    image: pawn,
  },
]


const nextSlide = () => {
  if (currentIndex.value < slides.length - 1) {
    currentIndex.value++
  }
}

const prevSlide = () => {
  if (currentIndex.value > 0) {
    currentIndex.value--
  }
}

const trackStyle = computed(() => ({
  transform: `translateX(-${currentIndex.value * 100}%)`,
}))
</script>



<template>
    <div class="carousel">
      <img :src="bg" class="carousel__background" />
  
      <button class="carousel__arrow left" @click="prevSlide">‹</button>
  
      <div class="carousel__viewport">
        <div class="carousel__track" :style="trackStyle">
          <div
            class="carousel__slide"
            v-for="(slide, index) in slides"
            :key="index"
          >
            <img :src="slide.image" alt="" class="carousel__piece" />
            <div class="carousel__content">
              <h2 class="carousel__title">{{ slide.title }}</h2>
              <p class="carousel__text">{{ slide.text }}</p>
            </div>
          </div>
        </div>
      </div>
  
      <button class="carousel__arrow right" @click="nextSlide">›</button>
    </div>
  </template>
  
  

  <style scoped lang="scss">
.carousel {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background-color: black;
  border-radius: pxToRem(24px);

  &__background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 0;
    pointer-events: none;
  }

  &__viewport {
    position: relative;
    overflow: hidden;
    z-index: 1;
    height: 100%;
  }

  &__track {
    display: flex;
    transition: transform 0.6s ease;
    height: 100%;
  }

  &__slide {
    min-width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: pxToRem(16px);
    color: white;
    font-family: 'Hedvig Letters Serif', serif;
    padding: 0 40px;
  }

  &__piece {
    width: 150px;
    height: auto;
  }

  &__content {
    max-width: 400px;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  &__title {
    font-size: 2rem;
  }

  &__text {
    font-size: 1rem;
  }

  &__arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 3rem;
    background: none;
    border: none;
    color: white;
    cursor: pointer;
    z-index: 2;

    &.left {
      left: 1rem;
    }

    &.right {
      right: 1rem;
    }
  }
}
</style>
