<template>
  <button v-if="type === 'main'" class="button">Начать игру</button>
  <button v-if="type === 'like'" class="button__like" @click="addLike">
    <slot></slot>
  </button>
  <button v-if="type === 'fliped'" class="button__fliped" @click="fliped">
    перевернуть
  </button>
  <button v-if="type === 'accept'" class="button__check" @click="check">
    <slot></slot>
  </button>
  <button v-if="type === 'error'" class="button__check" @click="check">
    <slot></slot>
  </button>
</template>
<script setup>
defineProps({
  type: {
    type: String,
    required: true,
  },
});

const emits = defineEmits(["addLike", "fliped", "check"]);

const fliped = () => {
  emits("fliped");
};

const addLike = () => {
  emits("addLike");
};

const check = () => {
  emits("check");
};
</script>

<style lang="scss" scoped>
.button {
  width: 315px;
  height: 65px;
  padding: 10px 16px;
  font-family: var(--font);
  font-weight: 400;
  font-size: 24px;
  color: var(--color-primary);
  background: #008bfe;
  border-radius: 50px;
  border: none;
  outline: none;
  cursor: pointer;
  &__like {
    outline: none;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    background: var(--color-bg-like);
  }
  &__fliped {
    outline: none;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    background: var(--color-primary);
    text-transform: uppercase;
    font-weight: 700;
    letter-spacing: 1.5px;
  }
  &__check {
    outline: none;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    background: var(--color-primary);
  }
}
</style>
