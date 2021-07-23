<template>
  <div class="container">
    <p @click="$emit('check', checkValue)" class="box">
      {{ answer }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Answer",
  props: {
    answer: String,
  },
  data() {
    return {
      checkValue: this.answer,
    };
  },
};
</script>
