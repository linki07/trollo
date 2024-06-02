<template>
  <div>
    <div class="modal" tabindex="-1" id="createColumn">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="createCard">Create a column</h5>
            <button type="button" class="btn-close" aria-label="Close" data-bs-dismiss="modal"></button>
          </div>
          <div class="modal-body">
            <form @submit.prevent="createColumn">
              <div class="mb-3">
                <label for="titleColumn" class="form-label">Set Column Title</label>
                <input
                  v-model="column.titleColumn"
                  type="text"
                  class="form-control"
                  id="titleColumn"
                  aria-describedby="titleColumn"
                  >
              </div>
            </form>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
            <button type="button" class="btn btn-primary" @click="createColumn" data-bs-dismiss="modal">Create</button>
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
      column:
      {
        id: Date.now(),
        titleColumn: '',
        tasks: [],
      },
    }
  },
  methods: {
    createColumn() {
      this.column.id = Date.now();
      this.column.tasks = []
      this.$emit('create', this.column)
      this.column = {
        titleColumn: '',
        tasks: [],
      }
    },
  }
}
</script>
<style scoped>

</style>