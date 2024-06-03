<template>
  <div>
    <div class="main container vh-100 position-relative overflow-auto">
      <Navbar/>
      <Sidebar/>
      <BoardList/>
      <Column v-bind:columns="columns"/>
    </div>

    <ModalCreateColumn
      v-for="column in columns"
      @create="createColumn"
      v-bind:column="column"
    />
    <ModalCreateTask v-bind:columns="columns"/>
  </div>
</template>
<script>
import Sidebar from '@/components/Sidebar.vue';
import Navbar from '@/components/Navbar.vue';
import BoardList from '@/components/BoardList.vue';
import Column from '@/components/Column.vue';
import ModalCreateTask from '@/components/ModalCreateTask.vue';
import ModalCreateColumn from '@/components/ModalCreateColumn.vue';

export default {
  components: {
    Sidebar, Navbar, BoardList, Column, ModalCreateTask, ModalCreateColumn
  },

  data() {
    return {
      columns: [
        {
          id: Date.now(),
          titleColumn: 'To Do',
          tasks: [],
        },
      ],
    }
  },
  methods: {
    createColumn(column) {
      this.columns.push(column);
    },
  },
}
</script>
<style scoped>

</style>