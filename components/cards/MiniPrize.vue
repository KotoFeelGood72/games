<template>
  <div class="cardPrize" :class="isColor">
    <div class="cardPrize__img">
      <img :src="card.img" />
    </div>
    <div class="cardPrize__txt">{{ card.name }}</div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
const props = defineProps<{
  card: any;
}>();

const isColor = computed(() => {
  switch (props.card.color) {
    case "violet":
      return "color_violet";
    case "green":
      return "color_green";
    case "blue":
      return "color_blue";
    case "rose":
      return "color_rose";
  }
});
</script>

<style scoped lang="scss">
.cardPrize__img {
  max-width: 10.6rem;
  @include flex-center;
  margin-bottom: 1.25rem;
  z-index: 1;
  transition: all 0.3s ease-in-out;
  img {
    width: 100%;
    height: 100%;
  }
}

.cardPrize__txt {
  font-size: 1.2rem;
  font-family: $font_5;
  z-index: 1;
}

.cardPrize {
  position: relative;
  z-index: 1;
  width: 17rem;
  height: 11rem;
  @include flex-center;
  flex-direction: column;
  cursor: pointer;

  &:hover {
    .cardPrize__img {
      transform: rotate(-5deg);
    }
    &:after {
      transform: translate(-50%, -60%);
    }
  }

  &:before {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100%;
    height: 100%;
    transform: translate(-50%, -50%);
    content: "";
    background-image: url("../../assets/img/prize/prize-before-blue.png");
    background-position: center center;
    background-repeat: no-repeat;
    background-size: contain;
    z-index: 0;
    pointer-events: none;
  }
  // &:after {
  //   position: absolute;
  //   top: 64%;
  //   left: 50%;
  //   width: 100%;
  //   height: 100%;
  //   transform: translate(-50%, -50%);
  //   content: "";
  //   background-image: url("../../assets/img/prize/prize-after-blue.png");
  //   background-position: center center;
  //   background-repeat: no-repeat;
  //   background-size: contain;
  //   z-index: -1;
  //   pointer-events: none;
  //   transition: all 0.3s ease-in-out;
  // }
  &.color_violet {
    &:before {
      background-image: url("../../assets/img/prize/prize-before-violet.png");
    }
    &:after {
      background-image: url("../../assets/img/prize/prize-after-violet.png");
    }
  }
  &.color_green {
    &:before {
      background-image: url("../../assets/img/prize/prize-before-green.png");
    }
    &:after {
      background-image: url("../../assets/img/prize/prize-after-green.png");
    }
  }
  &.color_blue {
    &:before {
      background-image: url("../../assets/img/prize/prize-before-blue.png");
    }
    &:after {
      background-image: url("../../assets/img/prize/prize-after-blue.png");
    }
  }
  &.color_rose {
    &:before {
      background-image: url("../../assets/img/prize/prize-before-rose.png");
    }
    &:after {
      background-image: url("../../assets/img/prize/prize-after-rose.png");
    }
  }
}
</style>
