<template>
  <v-card
    style="
      display: flex;
      justify-content: start;
      align-items: center;
      padding: 10px;
    "
  >
    <v-text-field v-model="newItemText" />
    <v-btn v-on:click="addNewTodo">Add</v-btn>
  </v-card>
</template>
<script>
export default {
  props: ["tasks"],
  data() {
    return {
      newItemText: "",
    };
  },
  methods: {
    addNewTodo() {
      this.$props.tasks.push({ action: this.newItemText, done: false });
      this.newItemText = "";
    },
  },
};
</script>
