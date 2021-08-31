<style lang="postcss">
div.container {
  max-width: 50%;
  border: 1px solid red;
  margin: auto;
  padding: 0.25rem;
}
.accordion {
  border: 1px solid green;
}
</style>
<template>
  <div class="container">
    <Accordion class="test" style="color: red">Test</Accordion>
  </div>
</template>

<script>
import Accordion from "../src/Accordion.vue";

export default {
  components: {
    Accordion,
  },
};
</script>