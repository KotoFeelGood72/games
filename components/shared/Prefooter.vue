<template>
  <div class="prefooter">
    <div class="container">
      <div class="prefooter_main">
        <div
          class="prefooter_item"
          v-for="(item, i) in prefooter"
          :key="'prefootert-item-' + i"
        >
          <div class="prefooter_item__img">
            <img :src="item.img" />
          </div>
          <div class="prefooter_item__content">
            <h6>{{ item.title }}</h6>
            <p>{{ item.txt }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const prefooter = ref<any>([
  {
    img: "/assets/img/prefooter/prefooter-4.svg",
    title: "9.780",
    txt: "Всего открыто кейсов",
  },
  {
    img: "/assets/img/prefooter/prefooter-1.svg",
    title: "10.450",
    txt: "Всего открыто кейсов",
  },
  {
    img: "/assets/img/prefooter/prefooter-2.svg",
    title: "179.345",
    txt: "Сделано апгрейдов",
  },
  {
    img: "/assets/img/prefooter/prefooter-3.svg",
    title: "20.851",
    txt: "Создано контрактов",
  },
]);
</script>

<style scoped lang="scss">
.prefooter {
  position: relative;
  top: -5rem;
}
.prefooter_main {
  @include flex-space;
  max-width: 175rem;
  margin: 0 auto;

  gap: 7.6rem;
}

.prefooter_item {
  background: linear-gradient(180deg, #3270fb 0%, #573dc0 100%);
  border-radius: 2rem;
  @include flex-start;
  gap: 3rem;
  padding: 2rem 4rem;
  height: 14.1rem;
}

.prefooter_item__img {
}

.prefooter_item__content {
  h6 {
    font-size: 4.4rem;
    font-family: $font_5;
  }
  p {
    color: $light;
    font-size: 1.7rem;
    font-family: $font_4;
  }
}
</style>
