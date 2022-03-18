<template>
  <h2 style="background-color: blue; text-align: center ; color: white; padding: 5px; margin-bottom: 5px;">
    {{ personName }}'s Todo List
  </h2>
</template>
<script>
export default {
  props: ["personName"],
};
</script>
