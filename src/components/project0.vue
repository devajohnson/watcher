<template>
  <div>
    <div :class="{ hide: !isShow }" id="notShown">Content</div>
    <button @click="isShow = !isShow">click Me</button>
  </div>
</template>
<script>
export default {
  name: "ToggleDiv",
  data: function () {
    return {
      isShow: false,
    };
  },

  props: {
    msg: String,
  },
};
</script>
<style scoped>
.notShown {
  visibility: hidden !important;
}
</style>