<template lang="">
  <span class="header__like__count">{{ count }}</span>
</template>
<script setup>
defineProps({
  count: {
    type: Number,
    required: true,
  },
});
</script>
<style></style>
