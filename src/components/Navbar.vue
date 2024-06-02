<template>
  <div>
    <nav class="navbar navbar-expand-xl navbar-dark border-bottom p-3 position-relative">
      <div class="container">
        <i class="bi bi-grid-3x3-gap-fill  me-3 cursor-pointer"></i>
        <a class="navbar-brand" href="#">
          <i class="bi bi-trello"></i>
          Trello
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarBasic" aria-controls="navbarBasic" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse show gap-3" id="navbarBasic">
          <ul class="navbar-nav mb-2 mb-xl-0 gap-3">
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle " href="#" id="navbarDropdownMenuLink" role="button" data-bs-toggle="dropdown" aria-expanded="false">Workspaces</a>
              <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
              </ul>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle " href="#" id="navbarDropdownMenuLink1" role="button" data-bs-toggle="dropdown" aria-expanded="false">Recent</a>
              <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink1">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
              </ul>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle " href="#" id="navbarDropdownMenuLink2" role="button" data-bs-toggle="dropdown" aria-expanded="false">Templates</a>
              <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink2">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
              </ul>
            </li>
          </ul>
          <button class="btn btn-sm" type="button" aria-labelledby="createColumn" data-bs-toggle="modal" data-bs-target="#createColumn">Create column</button>
        </div>
      </div>
    </nav>
  </div>

</template>
<script>
export default {

}
</script>
<style scoped>
  .navbar {
    background-color: #29669c;
  }

  .navbar .btn {
    background-color: #5484b0;
  }
</style>