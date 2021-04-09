<template>
  <div class="columns is-mobile">
    <div class="column is-half is-offset-one-quarter">
      <nav class="navbar is-white is-spaced" role="navigation" aria-label="dropdown navigation">
        <div class="navbar-brand">
          <div class="navbar-item not-affect">
            <p class="is-size-4 has-text-weight-bold has-text-primary">
              Neptuno Planner
            </p>
          </div>
          <div class="navbar-burger burger" :class="{ 'is-active' : showNav }" data-target="navbarExampleTransparentExample" @click="showNav = !showNav">
            <span />
            <span />
            <span />
          </div>
        </div>
        <div class="navbar-menu" :class="{ 'is-active' : showNav }">
          <div class="navbar-start">
            <b-navbar-item v-for="(item, key) of items" :key="key" tag="router-link" :to="item.to">
              {{ item.title }}
            </b-navbar-item>
          </div>
          <div class="navbar-end">
            <div class="navbar-item">
              <div class="buttons">
                <a class="button is-primary">
                  <strong>Sign up</strong>
                </a>
                <a class="button is-light">
                  Log in
                </a>
              </div>
            </div>
          </div>
        </div>
      </nav>

      <Nuxt />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data () {
    return {
      items: [
        {
          title: 'Home',
          to: { name: 'index' }
        },
        {
          title: 'Tasks',
          to: { name: 'tasks' }
        },
        {
          title: 'Profile',
          to: { name: 'profile' }
        }
      ],
      showNav: false
    }
  }
}
</script>
