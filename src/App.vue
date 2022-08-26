<template>

<TheNavigation />

  <div class="container">

    <router-view v-slot="{Component}" class="view lef-sidebar" name="LeftSideBar">

        <transition name="fade" mode="out-in">

          <component :is="Component" :key="$route.path"></component>

        </transition>

    </router-view>

    <router-view v-slot="{Component}" class="main-view">

      <transition name="fade" mode="out-in">

        <component :is="Component" :key="$route.path"></component>

      </transition>

    </router-view>

  </div>

</template>

<script>
import TheNavigation from './components/TheNavigation.vue'

export default {
  name: 'App',
  components: {
    TheNavigation
  }
}
</script>

<style lang="css">
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.3s;
  }

  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }

  .container {
    display: flex;
  }

  .left-sidebar {
    width: 20%;
  }

  .main-view {
    width: 100%;
  }

</style>
