<template>
  <div>
    <div class="sidebar position-absolute vh-100 border-end close" @click="sidebarToggle">
      <div class="sidebar__button cursor-pointer position-absolute p-1 d-flex align-items-center justify-content-center" >
        <i class="bi bi-chevron-right "></i>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    sidebarToggle() {
      const sidebar = document.querySelector('.sidebar');

      sidebar.classList.toggle('show')
    }
  }
}
</script>
<style scoped>
  .sidebar {
    min-width: 250px;
    background-color: #29669c;
    z-index: 2;
    transition: all .5s;
  }

  .close {
    left: -230px;
  }

  .show {
    left: 0;
  }

  .sidebar__button {
    background-color: #255c8e;
    border-radius: 100%;
    border: .5px solid #fff;
    width: 35px;
    top: 20px;
    right: -20px;
  }
</style>