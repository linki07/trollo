<template>
  <div>
    <div class="column__task d-flex flex-column mb-3">
      <div class="bg-primary p-1 w-25 mb-2 rounded-2"></div>
      <p>{{ typeTask }}</p>
      <p>{{ taskDescription }}</p>
      <i class="dropdown bi bi-list-task text-primary" data-bs-toggle="dropdown">
        <ul class="dropdown-menu">
          <li class="dropdown-item">
            <button type="button" class="btn btn-sm" @click="editTask">Edit</button>
          </li>
        </ul>
      </i>
      <div class="task__edit d-flex border-1 gap-3 align-items-center" v-if="isEditing">
        <div>
          <input class="form-control mb-3" type="text" v-model="editedTypeTask">
          <input class="form-control" type="text" v-model="editedTaskDescription">
        </div>

        <button type="button" class="btn btn-sm bg-primary" @click="saveEdit">Save</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    typeTask: {
      type: String,
      required: true,
    },
    taskDescription: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      isEditing: false,
      editedTypeTask: this.typeTask,
      editedTaskDescription: this.taskDescription,
    };
  },
  methods: {
    editTask() {
      this.isEditing = true;
    },
    saveEdit() {
      this.isEditing = false;
      this.$emit('update:typeTask', this.editedTypeTask);
      this.$emit('update:taskDescription', this.editedTaskDescription);
    },
  },
}
</script>

<style scoped>
.dropdown:before{
  cursor: pointer;
}
</style>