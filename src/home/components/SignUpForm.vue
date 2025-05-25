<script setup lang="ts">
import bg from '@/common/assets/Bg1.jpg'
import logo from '@/common/assets/pawn.svg'
</script>

<template>
  <article class="signup" :style="{ backgroundImage: `url(${bg})` }">
    <div class="signup__form__container">
      <img class="signup__form__container__logo" :src="logo" alt="Pawn Logo" />
      <h1 class="signup__form__title">Sign Up</h1>
      <form class="signup__form">
        <div class="signup__form__input__fields">
          <div class="signup__form__input">
            <input type="text" id="email" name="email" required placeholder="Email" />
          </div>
          <div class="signup__form__input">
            <input type="password" id="password" name="password" required placeholder="Password" />
          </div>
        </div>
        <div class="signup__form__input">
          <button class="btn" type="submit">Register</button>
        </div>
      </form>
    </div>
  </article>
</template>

<style scoped lang="scss">
.signup {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  background-size: cover;
  background-position: bottom center;
  border-radius: pxToRem(24px);
  color: var(--white);
  font-family: 'Hedvig Letters Serif';
  font-size: pxToRem(24px);
  padding: 32px;
}

.signup__form {
  .signup__form__input__fields {
    display: flex;
    flex-direction: column;
    gap: pxToRem(24px);
    margin-bottom: pxToRem(32px);
  }

  .signup__form__input {

    input,
    button {
      position: relative;
      z-index: 2;
      padding-left: pxToRem(28px);
      background: rgba(141, 44, 205, 0.5);
      backdrop-filter: blur(pxToRem(50px));
      border-radius: pxToRem(24px);
      border: none;
      color: var(--white);

      &::before {
        content: '';
        position: absolute;
        inset: 0;
        pointer-events: none;
        /* soft */
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25), inset 0px 25px 51px -36px rgba(255, 255, 255, 0.5), inset 0px 2px 11px -4px #FFFFFF, inset 0px 98px 100px -64px rgba(202, 172, 255, 0.3), inset 0px 4px 18px rgba(154, 146, 210, 0.3), inset 0px 1px 0px rgba(227, 222, 255, 0.2);
        border-radius: pxToRem(24px);
        z-index: 10000;
      }
    }


    button {
      padding: pxToRem(7px) pxToRem(18px);
      cursor: pointer;
    }
  }
}
</style>
