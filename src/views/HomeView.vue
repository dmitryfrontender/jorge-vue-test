<template>
  <div class="wrapper">
    <h1>We make  creative media that <span class="highlight">adds value</span></h1>

    <div class="container">
      <div class="row">
        <div v-for="thumb in thumbs" :key="thumb.id" class="col col-4">
          <ThumbComponent :item="thumb" />
        </div>
      </div>

      <div class="row">
        <div class="col col-12">
          <ButtonComponent>
            Get STARTED
          </ButtonComponent>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import ButtonComponent from '@/components/ButtonComponent.vue';
import { ref } from 'vue';
import ThumbComponent from '@/components/ThumbComponent.vue';

const thumbs = ref([]);

fetch('./data/thumbsData.json')
  .then((response) => {
    if (!response.ok) {
      throw new Error('Response was not ok');
    }
    return response.json();
  })
  .then((data) => {
    thumbs.value = data;
  })
  .catch((error) => {
    console.error('Fetch error:', error);
  });
</script>

<style lang="scss">
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Poppins", sans-serif;
  margin: 0;
}

h1 {
  font-size: 56px;
  font-weight: 700;
  line-height: 55px;
  text-align: center;
  color: #1B264F;
  margin: 0 auto;
  max-width: 730px;
  font-style: normal;
  letter-spacing: -0.56px;
  margin-bottom: 80px;

  .highlight {
    color: #506BCA;
  }
}

.wrapper {
  width: 100%;
  padding: 109px 0;
}

.container {
  max-width: 1373px;
  width: calc(100% - 30px);
  margin: 0 auto;
  padding: 0 15px;
}

.row {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 0 -15px 80px;

  &:last-child {
    margin-bottom: 0;
  }
}

.col {
  display: flex;
  align-items: center;
  justify-content: center;

  &-4 {
    width: 33.3%;

    @media (max-width: 1023px) {
      width: 50%;
    }

    @media (max-width: 767px) {
      width: 100%;
    }
  }

  &-12 {
    width: 100%;
  }
}
</style>
