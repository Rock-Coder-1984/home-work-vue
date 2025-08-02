<template>
  <header class="header">
    <p class="header__title">Запомни слово</p>
    <div class="header__like">
      <span class="header__like__count">{{ likes }}</span>
      <Button type="like" @addLike="addLike"><HeartIcon /></Button>
    </div>
  </header>
</template>
<script setup>
import { ref } from "vue";
import HeartIcon from "../icons/HeartIcon.vue";

import Button from "./Button.vue";

let likes = ref(100);

const addLike = () => {
  likes.value++;
  return likes.value;
};
</script>
<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 49px 66px;
  color: var(--color-secondary);
  &__title {
    text-transform: uppercase;
  }
  &__like {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 110px;
    height: 48px;
    background: var(--color-bg-like);
    color: #008bfe;
    border-radius: 36px;
    &__count {
      margin-right: 10px;
    }
  }
}
</style>
