<template>
  <div class="images-block-component">
    <ImageComponent
      v-for="image in props.images"
      :key="image.id"
      :src="image.url"
      :alt="image.alt"
    />
  </div>
</template>

<script setup>
import ImageComponent from '@/components/ImageComponent.vue';

const props = defineProps({
  images: {
    type: Array,
    required: true,
  },
});
</script>

<style lang="scss">
.images-block-component {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 3px;
}
</style>
