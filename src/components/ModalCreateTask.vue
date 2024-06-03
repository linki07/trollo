<template>
  <div>
    <div class="modal" tabindex="-1" v-for="(column, index) in columns" :key="column.id" :id="'createCard' + index">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="createCard">Create a card</h5>
            <button type="button" class="btn-close" aria-label="Close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body">
            <form @submit.prevent="createTask">
              <div class="mb-3">
                <label for="typeTask" class="form-label">Type of task</label>
                <input
                  v-model="task.typeTask"
                  type="text"
                  class="form-control"
                  id="typeTask"
                  aria-describedby="typeTask"
                  >
              </div>
              <div class="mb-3">
                <label for="taskDescription" class="form-label">Description</label>
                <input
                  v-model="task.taskDescription"
                  type="text"
                  class="form-control"
                  id="taskDescription"
                  >
              </div>
            </form>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
            <button type="button" class="btn btn-primary" @click="createTask(index)"data-bs-dismiss="modal">Create</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    columns: {
      type: Array,
      requared: true,
    },
  },
  data() {
    return {
      task:
      {
        id: Date.now(),
        typeTask: '',
        taskDescription: '',
      },
    }
  },
  methods: {
    createTask(index) {
      this.task.id = Date.now();
      this.$emit('create', this.task, index, this.task.id)
      this.columns[index].tasks.push(this.task);
      this.task = {
        typeTask: '',
        taskDescription: '',
      }
    },
  }
}
</script>
<style scoped>

</style>