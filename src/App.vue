<template>
  <div id="app">
    <div class="off-canvas off-canvas-sidebar-show">
      <!-- off-screen toggle button -->
      <a class="off-canvas-toggle btn btn-primary btn-action" href="#sidebar-id">
        <i class="icon icon-menu"></i>
      </a>

      <!-- off-screen sidebar -->
      <div id="sidebar-id" class="off-canvas-sidebar">
        <div class="brand">
          <router-link to="/" class="logo">
            <img src="./assets/logo.svg" alt="SongDrive Song Management Tool">
            <h2>SONGDRIVE</h2>
          </router-link>
        </div>
        <ul class="menu text-uppercase">
          <li class="divider"></li>
          <li class="menu-item">
            <router-link to="/">Dashboard</router-link>
          </li>
          <li class="menu-item">
            <div class="menu-badge">
              <label class="label label-primary">203</label>
            </div>
            <router-link to="/songs">Songs</router-link>
          </li>
          <li class="menu-item pb-2">
            <div class="menu-badge">
              <label class="label label-primary">132</label>
            </div>
            <router-link to="/setlists">Setlists</router-link>
          </li>
          <li class="divider" data-content="ACCOUNT">
          <li class="menu-item pt-2 pb-2">
            <div class="tile tile-centered">
              <div class="tile-icon"><img class="avatar" src="http://media.devmount.de/profile.jpg" alt="Avatar"></div>
              <div class="tile-content">
                Andreas Müller
              </div>
            </div>
          </li>
          <li class="menu-item pt-2">
            <router-link to="/profile"><i class="icon icon-people mr-2"></i> Profile</router-link>
          </li>
          <li class="menu-item">
            <router-link to="/settings"><i class="icon icon-edit mr-2"></i> Settings</router-link>
          </li>
          <li class="menu-item">
            <a href=""><i class="icon icon-arrow-right mr-2"></i> Logout</a>
          </li>
        </ul>
      </div>
      <a class="off-canvas-overlay" href="#close"></a>

      <!-- off-screen content -->
      <div class="off-canvas-content">
        <router-view/>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
$primary-color: #88b544;
$error-color: #ed2f47;
$body-font-color: #798a8e;
$bg-color: #161819;
$bg-color-light: #1b1e1f;
$bg-color-dark: #2c3638;
$border-color: #222627;

@import "node_modules/spectre.css/src/spectre";
@import "node_modules/spectre.css/src/spectre-icons";
@import "node_modules/spectre.css/src/spectre-exp";

.off-canvas .off-canvas-content {
    min-height: 100vh;
}

.brand {
  padding: 1em 1em 0 1em;

  .logo {
    padding: .3em 0;

    img {
      display: inline-block;
      width: 32px;
    }
    h2 {
      display: inline-block;
      font-size: 1.1rem;
      font-weight: 700;
      line-height: 1.6rem;
      margin-bottom: 0;
      margin-left: .5rem;
      margin-right: .5rem;
    }
  }
}

.menu {
  box-shadow: none;
  background: $bg-color;

  .divider[data-content]::after {
    background: $bg-color;
  }

  .menu-item {
    a {
      &:hover {
        background: #202718;
      }

      &.router-link-exact-active {
        background: #202718;
        color: $primary-color;
      }
    }
  }
}
</style>
