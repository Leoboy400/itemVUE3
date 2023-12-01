<template>
  <header class="header">
    <nav class="nav">
      <div class="nav__buttons">
        <div><button class="btn home">home</button></div>
        <div><button class="btn calc">calc</button></div>
        <div class="logo">
          <h1>LOGO</h1>
        </div>
      </div>
      <div class="nav__login">
        <button class="btn login">login</button>
      </div>
    </nav>
  </header>
</template>
<script>
import { defineComponent, ref, reactive } from "vue";
export default defineComponent({
  setup() {
    let testText = ref("Test Text");

    return {
      testText,
    };
  },
});
</script>
<style lang="scss">
.btn {
  border: 0px;
  background-color: #70252500;
  cursor: pointer;
}

.nav {
  display: flex;
  justify-content: space-between;
  @media (max-width: 660.999px) {
    flex-direction: column;
  }
  .nav__login {
    .login {
      background-color: var(--main-color);
      color: #fff;
      padding: 20px 0px;
      font-weight: bold;
      font-size: 18px;
      position: relative;
      width: 100px;
      height: 100%;
      color: #fff;
      z-index: 10;

      &:hover {
        background-color: #3c4b8a;
      }
    }
  }

  .nav__buttons {
    display: flex;
    align-items: center;
    position: relative;
    margin-top: 20px;
    color: #fff;
    // background-color: #253470;

    &::before {
      content: "";
      position: absolute;
      width: 500px;

      height: 20px;
      top: -20px;
      left: 0;
      background-color: var(--main-color);
    }
    @media (max-width: 660.999px) {
      &::before {
        content: "";
        position: absolute;
        max-width: 100%;
        height: 32px;
        top: -20px;
        left: 0;
        background-color: var(--main-color);
      }
    }

    .logo {
      font-size: 25px;
      padding: 20px 30px;
      background-color: #ffffff;
      border: 0px;

      h1 {
        z-index: 10;
        position: relative;
        color: var(--main-color);
      }
    }

    div {
      background-color: var(--main-color);
      border-right: 1px solid #000;
      height: 100%;

      .btn {
        padding: 20px 0px;
        font-weight: bold;
        font-size: 18px;
        position: relative;
        width: 100px;
        height: 100%;
        color: #fff;
        z-index: 10;

        &:hover {
          background-color: #3c4b8a;
        }
      }
    }
  }
}

@media (max-width: 420.999px) {
}
</style>
