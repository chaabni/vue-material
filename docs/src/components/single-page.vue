<template>
  <div class="page-content single-page">
    <md-whiteframe md-elevation="1" class="main-header">
      <md-toolbar>
        <md-button class="md-icon-button" @click="toggleSidenav">
          <md-icon>menu</md-icon>
        </md-button>

        <div class="md-title">
          <span class="page-title">{{ label }}</span>
        </div>

        <md-button href="https://github.com/marcosmoura/vue-material" target="_blank" rel="noopener" class="md-icon-button github-button">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1024 1024"><path fill="#ffffff" d="M512 0C229.25 0 0 229.25 0 512c0 226.25 146.69 418.13 350.16 485.81 25.59 4.69 34.94-11.12 34.94-24.62 0-12.19-0.47-52.56-0.72-95.31C242 908.81 211.91 817.5 211.91 817.5c-23.31-59.12-56.84-74.87-56.84-74.87-46.53-31.75 3.53-31.12 3.53-31.12 51.41 3.56 78.47 52.75 78.47 52.75 45.69 78.25 119.88 55.63 149 42.5 4.65-33 17.9-55.62 32.5-68.37C304.91 725.44 185.34 681.5 185.34 485.31c0-55.94 19.97-101.56 52.66-137.41-5.22-13-22.84-65.09 5.06-135.56 0 0 42.94-13.75 140.81 52.5 40.81-11.41 84.59-17.03 128.13-17.22 43.5 0.19 87.31 5.88 128.19 17.28 97.69-66.31 140.69-52.5 140.69-52.5 28 70.53 10.38 122.56 5.13 135.5 32.81 35.84 52.63 81.47 52.63 137.41 0 196.69-119.75 240-233.81 252.69 18.44 15.88 34.75 47 34.75 94.75 0 68.44-0.69 123.63-0.69 140.5 0 13.63 9.31 29.56 35.25 24.56C877.44 930 1024 738.13 1024 512 1024 229.25 794.75 0 512 0z"></svg>
        </md-button>
      </md-toolbar>
    </md-whiteframe>

    <div class="single-page-content">
      <slot></slot>
    </div>
  </div>
</template>

<style lang="scss">
  @import '../../../src/core/stylesheets/variables.scss';

  .single-page-content {
    width: 100%;
    max-width: 1024px;
    margin: 0 auto;
    padding: 16px;
  }

  .single-page {
    padding-top: 64px;

    .main-header {
      position: fixed;
      top: 0;
      right: 0;
      left: 0;
      z-index: 2;
      transition: $swift-ease-out;

      @media (min-width: 1280px) {
        padding-left: 280px;
      }

      .md-toolbar,
      .md-title {
        color: #fff;
      }
    }
  }

  .single-page-home {
    padding-top: 256px;
  }

  .single-page-banner {
    min-height: 256px;
    padding-top: 98px;
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    z-index: 3;
    color: #fff !important;

    .md-title:first-child {
      margin-left: 48px;
      font-size: 45px;
      font-weight: 400;
      line-height: 1.3em;
    }
  }

  .single-page-menu-trigger {
    margin: 0;
    position: fixed;
    top: 12px;
    left: 8px;
    z-index: 3;
    color: #fff;
  }

  .md-button.github-button {
    margin: 0;
    position: fixed;
    top: 12px;
    right: 12px;
    z-index: 3;
  }
</style>

<script>
  export default {
    props: ['label'],
    methods: {
      toggleSidenav() {
        this.$root.toggleSidenav();
      }
    },
    mounted() {
      document.title = 'Vue Material - ' + this.label;
    }
  };
</script>
