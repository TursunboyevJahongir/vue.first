<template>
  <div class="message">
    <p>Messages -- {{ message }}</p>
  </div>
</template>

<script>
export default {
  props: {
    message: {
      type: String,
      required: true,
      // default:"message"
    },
  },
};
</script>

<style scoped>
p {
  text-align: center;
  color: red;
}
</style>
