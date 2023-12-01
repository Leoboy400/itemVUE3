<template>
  <div class="card">
    <div class="card__img"><img alt="" :src="cardUrlImg" /></div>
    <div class="card__text">
      <h2>{{ cardTitle }}</h2>
      <p>{{ cardText }}</p>
    </div>
  </div>
</template>
<script>
import { defineComponent } from "vue";
export default {
  props: { cardTitle: "", cardText: "", cardUrlImg: "" },
  setup(props) {
    return {
      cardTitle: props.cardTitle,
      cardText: props.cardText,
      cardUrlImg: props.cardUrlImg,
    };
  },
};
</script>
<style lang="scss">
.card__img {
  width: 100%;
  height: 100px;
  img {
    width: 100%;
    max-width: 1400px;
    max-height: 1000px;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }
}
</style>
