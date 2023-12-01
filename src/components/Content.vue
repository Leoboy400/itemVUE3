<template>
  <section class="content">
    <div class="side__bar">
      <NavList :dataId="identifier" :checkIdProps="checkId" />
    </div>
    <div class="main__content">
      <div class="cards">
        <Card
          v-show="card.visible"
          v-for="card in cards"
          :cardUrlImg="card.img"
          :cardTitle="card.title"
          :cardText="card.text"
        />
      </div>
    </div>
  </section>
</template>
<script>
import { ref, reactive } from "vue";
import NavList from "./UI/NavList.vue";
import Card from "./UI/Card.vue";

export default {
  components: { NavList, Card },
  setup() {
    let identifier = reactive([1, 2, 3, 4]);
    let cards = reactive([
      {
        id: identifier[0],
        visible: true,
        img: "../../src/assets/img/pre.jpg",
        title: "Title1",
        text:
          "Многие поклонники любят смотреть аниме онлайн, однако для этого часто приходится пользоваться несколькими источниками, поскольку ни один из них нельзя назвать универсальным. Но у нас есть отличная новость для любителей аниме! Мы запустили новый проект AnimeGO, посвящённый онлайн-просмотру аниме. Теперь Вам не придётся бороздить просторы интернета в поисках любимого тайтла – все лучшие аниме в хорошем качестве уже есть на нашем портале. Мы сами очень любим этот жанр и поэтому постарались сделать наш сайт как можно более удобным и захватывающим.",
      },
      {
        id: identifier[1],
        visible: false,
        img: "../../src/assets/img/pre5.jpg",
        title: "Title2",
        text:
          "watch's first argument can be different types of reactive : it can be a ref (including computed refs), a reactive object, a getter function, or an array of multiple sources:",
      },
      {
        id: identifier[2],
        visible: false,
        img: "../../src/assets/img/pre3.jpg",
        title: "Title3",
        text:
          "With Composition API, we can use the watch function to trigger a callback whenever a piece of reactive state changes:",
      },
      {
        id: identifier[3],
        visible: false,
        img: "../../src/assets/img/pre4.jpg",
        title: "Title4",
        text:
          "Computed properties allow us to declaratively compute derived values. However, there are cases where we need to perform  in reaction to state changes - for example, mutating the DOM, or changing another piece of state based on the result of an async operation.",
      },
    ]);
    const checkId = (id) => {
      cards.forEach((e) => {
        if (id == e.id) {
          e.visible = true;
        } else {
          e.visible = false;
        }
      });
    };
    return {
      cards,
      identifier,
      checkId,
    };
  },
};
</script>
<style lang="scss">
.content {
  display: flex;
  margin-top: 40px;

  .main__content {
    padding-left: 30px;
  }
}
@media (max-width: 420.999px) {
  .content {
    flex-direction: column;
    .main__content {
      padding-top: 30px;
      padding-left: 0px;
    }
  }
}
</style>
