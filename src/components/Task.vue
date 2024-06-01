<template>
  <div class="column__task d-flex flex-column mb-3">
    <div class="bg-primary p-1 w-25 mb-2 rounded-2"></div>
    <p>{{ typeTask }}</p>
    <!-- <input type="text"
    v-model="typeTask"
    > -->
    <p>{{ taskDescription }}</p>
    <i class="dropdown bi bi-list-task text-primary cursor-pointer" data-bs-toggle="dropdown">
      <ul class="dropdown-menu">
        <li class="dropdown-item">
          <button type="button" class="btn btn-sm" @click="editTask">Edit</button>
        </li>
      </ul>
    </i>
  </div>
</template>
<script>
export default {
  props: {
    columns: {
      type: Array,
      requared: true,
    },
    typeTask: {
      type: String,
      requared: true,
    },
    taskDescription: {
      type: String,
      requared: true,
    },
  },
  methods: {
    editTask() {
      console.log(this.columns)
    }
  },
}
</script>
<style></style>