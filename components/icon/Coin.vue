<template>
  <icon-lottie :json="json" />
</template>

<script>
  import IconLottie from './Lottie'
  import json from '~/assets/icons/coin.json'

  export default {
    components: {
      IconLottie,
    },

    data() {
      return {
        json,
      }
    },
  }
</script>