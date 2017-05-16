<template lang="pug">
  div#app
    div#offCanvas.off-canvas.position-right(data-off-canvas)
      ul.sidebar-menu(data-close="offCanvas")
        li: router-link(to="/" exact) Home
        li: router-link(to="/reveal" exact) Reveal
        li: router-link(to="/slider" exact) Slider
        li: router-link(to="/tooltip" exact) Tooltip
        li: router-link(to="/dropdown-menu" exact) Dropdown Menu
        li: router-link(to="/drilldown-menu" exact) Drilldown Menu
        li: router-link(to="/accordion-menu" exact) Accordion Menu
        li: router-link(to="/magellan" exact) Magellan
        li: router-link(to="/accordion" exact) Accordion
        li: router-link(to="/dropdown" exact) Dropdown
        li: router-link(to="/tabs" exact) Tabs
        li: router-link(to="/orbit" exact) Orbit

    div.off-canvas-content(data-off-canvas-content)
      div.top-bar
        ul.menu.expanded
          li.logo: router-link(to="/") Vue-Foundation
          li: a.button.small.menu-button(data-toggle="offCanvas") Menu

      div.content-wrapper
        router-view
</template>

<script>
export default {
  name: 'app',
  mounted() {
    this.offCanvas = new Foundation.OffCanvas($('#offCanvas'));
  },
};
</script>



<style lang="scss">  
  @import './styles/global';
  
  // Chrome Reset 
  a:focus {
    outline: none;
  }

  .logo, .logo a {
    color: $white;
    font-weight: normal;
  }

  li a.menu-button {
    border-radius: 20px;
    padding-left: 1.5rem;
    padding-right: 1.5rem; 
    font-weight: 600;
    text-transform: uppercase;
    display: inline-block;
    float: right;
  }

  .content-wrapper {
    padding: 0.75rem 0;
  }

  .sidebar-menu {
    @include menu-base();
    @include menu-direction(vertical);
    a {
      color: $secondary-color;
      font-weight: normal;
    }
    a.active {
      font-weight: 600;
      color: $primary-color;
    }
  }
</style>

