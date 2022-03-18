<template>
  <v-app>
    <v-container>
      <v-row>
        <div class="col-12">
          <div id="app">
            <TitleBar :personName="name" />
            <Tasks :tasks="filteredTasks" />
            <TaskCreater :tasks="tasks" />
            <div
              style="display: flex; justify-content: start; align-items: center"
            >
              <v-checkbox type="checkbox" v-model="hideCompleted" />
              <label>hideCompleted</label>
            </div>
          </div>
        </div>
      </v-row>
    </v-container>
  </v-app>
</template>
<script>
import TitleBar from "./components/TitleBar.vue";
import Tasks from "./components/TasksList.vue";
import TaskCreater from "./components/TaskCreater.vue";
export default {
  name: "app",
  components: { TitleBar, Tasks, TaskCreater },
  data() {
    return {
      name: "Mostafa",
      tasks: [
        { action: "Wake up", done: true },
        { action: "read a book", done: false },
        { action: "watch tv", done: true },
        { action: "write homework", done: false },
      ],
      hideCompleted: false,
    };
  },
  computed: {
    filteredTasks() {
      if (this.hideCompleted) return this.tasks.filter((task) => !task.done);
      else return this.tasks;
    },
  },
};
</script>
