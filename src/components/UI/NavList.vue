<template>
  <div class="position__list">
    <ul class="list" @click="addActive">
      <li :id="list.id" :class="list.class" v-for="list in lists">
        <span>{{ list.span }}</span> <img :src="list.src" :alt="list.alt" />
      </li>
    </ul>
  </div>
</template>
<script>
import { ref, reactive } from "vue";

export default {
  props: { dataId: Array, checkIdProps: Function },
  setup(props) {
    // props.checkIdProps(2);
    let lists = reactive([
      {
        id: props.dataId[0],
        span: "Position1",
        src: "../../../src/assets/img/burgar.png",
        alt: "стрелка",
        class: "list__item list__item-active",
        visible: true,
      },
      {
        id: props.dataId[1],
        span: "Position2",
        src: "../../../src/assets/img/burgar.png",
        alt: "стрелка",
        class: "list__item",
        visible: true,
      },
      {
        id: props.dataId[2],
        span: "Position3",
        src: "../../../src/assets/img/burgar.png",
        alt: "стрелка",
        class: "list__item",
        visible: true,
      },
      {
        id: props.dataId[3],
        span: "Position4",
        src: "../../../src/assets/img/burgar.png",
        alt: "стрелка",
        class: "list__item",
        visible: true,
      },
    ]);
    const addActive = (e) => {
      let target = e.target;
      lists.forEach((e) => {
        if (target.closest(".list__item").id == e.id) {
          e.class = "list__item list__item-active";
          props.checkIdProps(e.id);
        } else {
          e.class = "list__item";
        }
      });
    };

    return {
      addActive,
      lists,
      dataId: props.dataId,
      checkIdProps: props.checkIdProps,
    };
  },
};
</script>
<style lang="scss">
.list {
  list-style: none;
  margin: 0;
  padding: 0;
  max-height: 600px;

  .list__item {
    font-weight: bold;
    justify-content: space-between;
    background-color: #b3adad;
    cursor: pointer;
    display: flex;
    padding: 5px 15px;
    min-width: 200px;
    border: 1px solid #000;
    border-radius: 1px;
    margin-bottom: 10px;
    color: var(--main-color);

    &:hover {
      background-color: #d3d3d3;
    }
  }

  .list__item-active {
    background-color: var(--main-color);
    color: #d3d3d3;

    &:hover {
      background-color: var(--main-color);
    }
  }
}
</style>
