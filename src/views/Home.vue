<template>
  <div class="home">
    <div class="bg_logo">
      <img class="logo" alt="Vue logo" src="../assets/logo_.png" />
    </div>
    <div class="bg_container">
      <Container />
    </div>
    <div class="container_answers">
      <Answers />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import Container from "@/components/Container.vue";

export default {
  name: "Home",
  components: {
    Container,
  },
};
</script>
