<template>
    <header>
      {{  this.is_user }}
    <nav class="navbar navbar-expand-lg navbar-light bg-warning">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <!--  -->
          <ul class="navbar-nav mx-auto">
            <li class="nav-item">
              <router-link class="nav-link" to="/">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/about">About</router-link>
            </li>
            <li class="nav-item">
              <router-link 
                v-if="this.is_user"
                class="nav-link btn btn-primary text-light" 
                to="#"
              >Выход</router-link>
              <router-link 
                v-else
                class="nav-link btn btn-primary text-light" 
                to="/login"
              >Вход</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<script> 
export default {
  data()
  {
    return {
      is_user: localStorage.getItem('isAuth')
    }
  },
  methods: {
  }
}
</script>