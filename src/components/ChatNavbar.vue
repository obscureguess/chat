<template>
  <nav class="navbar navbar-light bg-light">
    <a class="navbar-brand" href="#">
      <img src="https://getbootstrap.com/docs/4.4/assets/brand/bootstrap-solid.svg" width="30" height="30" class="d-inline-block align-top" alt="">
      Bootstrap
    </a>
    <div class="ml-auto">
      <span class="nav-item">{{ user.username }} | </span>
      <a @click="onLogout" href="#" class="nav-item">Logout</a>
    </div>
  </nav>
</template>

<script>
import { mapState, mapActions } from 'vuex'

export default {
  name: 'ChatNavbar',
  computed: {
    ...mapState([
      'user'
    ])
  },
  methods: {
    ...mapActions([
      'logout'
    ]),
    onLogout () {
      this.logout()
      this.$router.push({ path: '/' })
    }
  }
}
</script>
