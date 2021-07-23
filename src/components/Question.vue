<template>
  <div class="container">
    <div class="box">
      <p>{{ questions }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    questions: String,
  },
};
</script>
