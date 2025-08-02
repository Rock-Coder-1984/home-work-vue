<template>
  <div v-if="type === 'front'" class="card">
    <div class="card__content">
      <div class="card__number">{{ number }}</div>
      <span class="card__name">{{ name }}</span>
      <div class="card__footer">
        <Button type="fliped" @fliped="fliped(number)" />
      </div>
    </div>
  </div>
  <div v-if="type === 'fliped'" class="card">
    <div class="card__content">
      <div class="card__number">{{ number }}</div>
      <span class="card__name">{{ name }}</span>
      <div class="card__footer card__footer_fliped">
        <Button type="accept" @check="check(number)"><AcceptIcon /></Button>
        <Button type="error" @check="check(number)"><ErrorIcon /></Button>
      </div>
    </div>
  </div>
</template>
<script setup>
import Button from "./Button.vue";
import AcceptIcon from "../icons/AcceptIcon.vue";
import ErrorIcon from "../icons/ErrorIcon.vue";

defineProps({
  type: {
    type: String,
    required: true,
  },
  number: {
    type: String,
    required: true,
  },
  name: { type: String, required: true },
});

const fliped = (number) => {
  console.log("fliped", number);
};

const check = (number) => {
  console.log("check", number);
};
</script>
<style lang="scss">
.card {
  width: 250px;
  height: 376px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 16px;
  background: var(--color-primary);
  position: relative;
  transition: all 0.3s;
  &:hover {
    cursor: pointer;
    transform: scale(1.1);
  }
  &__content {
    width: 212px;
    height: 320px;
    border: solid 1px var(--color-bg-like);
    border-radius: 12px;
  }
  &__number {
    position: absolute;
    width: 16px;
    height: 16px;
    background: var(--color-primary);
    top: 20px;
    left: 35px;
    color: var(--color-primary-inverted);
  }
  &__name {
    width: 180px;
    height: 21px;
    display: block;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: var(--color-primary-inverted);
    text-align: center;
  }
  &__footer {
    position: absolute;
    bottom: 19px;
    left: 73px;
    &_fliped {
      left: 89px;
      width: 80px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
  }
}
</style>
