<template>
  <div>
    <div class="row">
      <div class="col">Task</div>
      <div class="col">Done</div>
    </div>
    <div class="row" v-for="i in tasks" v-bind:key="i.action">
      <div class="col">{{ i.action }}</div>
      <div
        class="col"
        style="display: flex; justify-content: start; align-items: center"
      >
        <v-checkbox type="checkbox" v-model="i.done" /><span>{{ i.done }}</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["tasks"],
};
</script>
