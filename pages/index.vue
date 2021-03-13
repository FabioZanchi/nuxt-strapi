<template>
  <div class="container mx-auto px-4">
    <div class="banner-home shadow-2xl flex items-center mt-10">
      <div class="w-3/5 p-10">
        <h1 class="text-5xl font-medium mb-8">{{ this.home.banner_title }}</h1>
        <p class="text-2xl mb-16">{{ this.home.banner_description }}</p>
        <a
          class="ransition duration-300 ease-in-out p-3 bg-red-500 hover:bg-red-600 rounded text-white text-2xl"
          href="https://www.google.com"
          target="_blank"
          >{{ this.home.banner_button }}</a
        >
      </div>
    </div>
    <div class="flex justify-between">
      <div class="w-1/4 flex-col text-center justify-center my-16 mx-8 py-4">
        <icon-house class="icons w-40 h-40" />
        <h2 class="text-2xl text-gray-700 font-medium ">
          {{ this.home.house_icon_title }}
        </h2>
        <p class="text-lg">{{ this.home.house_icon_description }}</p>
      </div>
      <div class="w-1/4 flex-col text-center justify-center my-16 mx-8 py-4">
        <icon-microphone class="icons w-40 h-40" />
        <h2 class="text-2xl text-gray-700 font-medium ">
          {{ this.home.mic_icon_title }}
        </h2>
        <p class="text-lg">{{ this.home.mic_icon_description }}</p>
      </div>
      <div class="w-1/4 flex-col text-center justify-center my-16 mx-8 py-4">
        <icon-camera class="icons w-40 h-40" />
        <h2 class="text-2xl text-gray-700 font-medium ">
          {{ this.home.camera_icon_title }}
        </h2>
        <p class="text-lg">{{ this.home.camera_icon_description }}</p>
      </div>
      <div class="w-1/4 flex-col text-center justify-center my-16 mx-8 py-4">
        <icon-coin class="icons w-40 h-40 " />
        <h2 class="text-2xl text-gray-700 font-medium ">
          {{ this.home.coin_icon_title }}
        </h2>
        <p class="text-lg">{{ this.home.coin_icon_description }}</p>
      </div>
    </div>
    <div class="flex mb-10">
      <p class="text-lg">
        {{ this.home.last_paragraph }}
      </p>
    </div>
  </div>
</template>

<script>
import IconHouse from "~/components/icon/House.vue";
import IconCoin from "~/components/icon/Coin.vue";
import IconMicrophone from "~/components/icon/Microphone.vue";
import IconCamera from "~/components/icon/Camera.vue";
import axios from "axios";

export default {
  components: {
    IconHouse,
    IconCoin,
    IconMicrophone,
    IconCamera
  },
  data() {
    return {
      error: null,
      home: [],
    };
  },
  async mounted() {
    try {
      const response = await axios.get(
        "https://nuxt-strapi-cms.herokuapp.com/home"
      );
      this.home = response.data;
      console.log(this.home.banner_image.url);
    } catch (error) {
      this.error = error;
    }
  },
  methods: {}
};
</script>

<style scoped>
.banner-home {
  background-image: url('~assets/images/bg-home-1.jpg');
  background-size: cover;
  width: 100%;
  height: 600px;
}

.icons {
  margin: 0 auto;
}
</style>
