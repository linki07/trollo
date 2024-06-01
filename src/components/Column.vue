<template>
  <div class="column container p-3">
    <div class="row p-3 gy-5">
      <div class="col-lg-3 column__card" v-for="(column, index) in columns" :key="index">

        <div class="column__card-bg p-3 flex-column rounded-3">
          <div class="column__card-top d-flex justify-content-between">
            <!-- <p>{{ column.titleColumn }}</p> -->
            <input type="text"
              class="bg-transparent border-0 mb-3"
              v-model="column.titleColumn"
            >
            <i class="bi bi-three-dots"></i>
          </div>

            <draggable
              v-model="column.tasks"
              item-key="index"
              class="column__tasks d-flex flex-column mb-3"
            >
              <template #item="{element:task}">
                <Task
                @create="createTask"
                v-bind:typeTask="task.typeTask"
                v-bind:taskDescription="task.taskDescription"
                v-bind:id="task.id" />
              </template>
            </draggable>

          <div class="column__card-top-bottom text-primary">
            <button class="border-0 me-2 text-primary" aria-labelledby="createCard" data-bs-toggle="modal"
              :data-bs-target="'#createCard' + index">+ Add a card</button>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>
<script>
import Task from '@/components/Task.vue';
import draggable from 'vuedraggable';

export default {
  components: {
    Task, draggable
  },
  props: {
    columns: {
      type: Array,
      requared: true,
    },
  },
  data() {
    return {
      drag: true,
      column: [
        {
          id: Date.now(),
          titleColumn: 'To Do',
          tasks: [],
        },
      ],
    }
  },
  methods: {
    createTask() {
      this.column.tasks.push(this.task)
    },
  }
}
</script>
<style scoped></style>