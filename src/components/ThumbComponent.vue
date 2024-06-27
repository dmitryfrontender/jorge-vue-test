<template>
  <div class="thumb-component">
    <div class="thumb-component-wrapper">
      <div class="thumb-component-images">
        <ImagesBlockComponent :images="props.item.images" />
      </div>
      <div class="thumb-component-info">
        <h3>{{ props.item.title }}</h3>
        <ul v-if="props.item.list">
          <li v-for="list in props.item.list" :key="list.id">
            {{ list.text }}
          </li>
        </ul>
        <p v-if="props.item.description">{{ props.item.description }}</p>
        <p v-if="props.item.additionalDescription">{{ props.item.additionalDescription }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import ImagesBlockComponent from '@/components/ImagesBlockComponent.vue';

const props = defineProps({
  item: {
    type: Object,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
.thumb-component {
  padding: 20px 15px;
  width: calc(100% - 30px);
  height: calc(100% - 40px);

  &-wrapper {
    display: flex;
    border-radius: 8px;
    overflow: hidden;
    background: #FFF;
    width: 100%;
    height: 100%;
  }

  &-images {
    flex-grow: 0;
    flex-shrink: 0;
    width: 43%;
    height: 100%;
  }

  &-info {
    display: flex;
    width: 57%;
    flex-grow: 1;
    flex-shrink: 1;
    padding: 40px 30px 34px 34px;
    flex-direction: column;
    align-items: flex-start;
    align-self: stretch;

    h3 {
      color: #353844;
      font-feature-settings: 'salt' on, 'liga' off;
      font-family: "Poppins", sans-serif;
      font-size: 24px;
      font-style: normal;
      font-weight: 700;
      line-height: 32px;
      margin-bottom: 12px;
    }

    ul {
      margin: 0 0 12px;
      padding: 0;
      list-style: none;

      li {
        position: relative;
        padding-left: 17px;
        color: #353844;
        font-feature-settings: 'salt' on, 'liga' off;
        font-family: "Nunito Sans", sans-serif;
        font-size: 15px;
        font-style: normal;
        font-weight: 700;
        line-height: 26px;

        &:before {
          content: "";
          position: absolute;
          top: 50%;
          left: 0;
          transform: translateY(-50%);
          width: 6px;
          height: 6px;
          background: #D2AD81;
          border-radius: 50%;
        }
      }
    }

    p {
      margin: 0;
      color: #353844;
      font-feature-settings: 'salt' on, 'liga' off;
      font-family: "Nunito Sans", sans-serif;
      font-size: 15px;
      font-style: normal;
      font-weight: 600;
      line-height: 24px;
    }
  }
}
</style>
