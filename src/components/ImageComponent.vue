<template>
  <div class="image-component">
    <img
        :src="props.src"
        :alt="props.alt"
        :width="props.width"
        :height="props.height"
    />
  </div>
</template>

<script setup>
const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  alt: {
    type: String,
    required: true,
  },
  width: {
    type: String,
    default: '',
  },
  height: {
    type: String,
    default: '',
  },
});
</script>

<style lang="scss">
.image-component {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;

  img {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    min-width: 100%;
    min-height: 100%;
  }
}
</style>
