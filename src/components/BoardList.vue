<template>
  <div>
    <section class="boardList d-flex align-items-center align-content-center p-3 ms-3 gap-3 border-bottom position-relative">
      <div class="container">
        <div class="row">
          <div class="col-lg-2">
            <h2>Project A</h2>
          </div>
          <div class="col-lg-3">
            <div class="d-flex align-items-center align-content-center gap-3">
              <i class="bi bi-people-fill"></i>
              <span>Workspace visible</span>
              <ul class="navbar-nav">
              <li class="nav-item dropdown">
                <a class="nav-link dropdown-toggle " href="#" id="navbarDropdownMenuLink4" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                  <button class="btn btn-sm btn-secondary" type="button">
                    <i class="bi bi-kanban"></i>
                    Board
                    </button>
                </a>
                <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink4">
                  <li><a class="dropdown-item" href="#">Action</a></li>
                </ul>
              </li>
            </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>

</template>
<script>
export default {
}
</script>
<style scoped>
section {
  background-color: #255c8e;
  z-index: 1;
}
</style>