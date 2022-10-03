<template>
  <v-container>
    <v-row>
      <v-col v-for="tasksItem in tasksItems" :key="tasksItem.id" cols="4">
        <div class="task-card">
          <h3 class="task-card-title">{{ tasksItem.name }}</h3>
          <draggable
            class="task-card-draggable"
            :list="tasksItem.tasks"
            :key="tasksItem.id"
            group="tasks"
          >
            <div
              class="task-card-item"
              v-for="item in tasksItem.tasks"
              :key="item.id"
            >
              {{ item.name }}
            </div>
          </draggable>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import draggable from "vuedraggable";
export default {
  name: "TasksList",
  components: {
    draggable,
  },
  data: () => ({
    tasksItems: [
      {
        id: 1,
        name: "Обсуждение",
        tasks: [
          {
            id: 1,
            name: "Задача 1",
          },
          {
            id: 2,
            name: "Задача 2",
          },
        ],
      },
      {
        id: 2,
        name: "В работе",
        tasks: [
          {
            id: 3,
            name: "Задача 3",
          },
          {
            id: 4,
            name: "Задача 4",
          },
        ],
      },
      {
        id: 3,
        name: "Тестирование",
        tasks: [
          {
            id: 5,
            name: "Задача 5",
          },
          {
            id: 6,
            name: "Задача 6",
          },
          {
            id: 7,
            name: "Задача 7",
          },
        ],
      },
    ],
  }),
};
</script>
<style lang="scss">
.task-card,
.task-card-item {
  border: 1px solid #ddd;
  border-radius: 4px;
  background: #f2f2f2;
  padding: 10px;
}
.task-card-title {
  color: #444;
}
.task-card-item {
  background: #fff;
  margin: 10px 0;
}
</style>
