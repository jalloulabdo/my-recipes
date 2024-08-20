<template>
  <header>
    <div class="navbar navbar-default visible-xs">
      <button type="button" class="navbar-toggle collapsed" @click="toggleSidebar">
        <span class="sr-only">Toggle navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
      <router-link :to="{ name: 'home' }" class="navbar-brand">My recipes</router-link>
    </div>

    <nav class="sidebar" :class="{ 'sidebar-open': isSidebarOpen }">
      <div class="navbar-collapse" id="navbar-collapse">
        <div class="site-header hidden-xs">
          <router-link :to="{ name: 'home' }" class="site-brand">
            <img class="img-responsive site-logo" alt="" src="../assets/my-recipes-logo.png">
            My recipes
          </router-link>
          <p>Home cooks are our heroes—it's as simple as that. My recipe is a community built by and for kitchen experts: The cooks who will dedicate the weekend to a perfect beef bourguignon but love the simplicity of a slow-cooker rendition, too.</p>
        </div>
        <ul class="nav pb-4">
          <li><router-link :to="{ name: 'home' }">Home</router-link></li>
          <li><router-link :to="{ name: 'byName' }">Search Meals</router-link></li>
          <li><router-link :to="{ name: 'byLetter' }">Meals By Letter</router-link></li>
          <li><router-link :to="{ name: 'ingredients' }">Meals By Ingredients</router-link></li>
        </ul>

        <nav class="nav-footer">
          <p class="nav-footer-social-buttons">
            <a class="fa-icon" href="https://www.instagram.com/" title="">
              <i class="fa fa-instagram"></i>
            </a>
            <a class="fa-icon" href="https://dribbble.com/" title="">
              <i class="fa fa-dribbble"></i>
            </a>
            <a class="fa-icon" href="https://twitter.com/" title="">
              <i class="fa fa-twitter"></i>
            </a>
          </p>
          <p>© Untitled | Website created with 
            <a href="#" title="Create website with free html template">My recipes</a> /
            <a href="https://www.unsplash.com/" title="Beautiful Free Images">Unsplash</a>
          </p>
        </nav>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isSidebarOpen: false, // Sidebar initially closed for mobile/tablet
    };
  },
  methods: {
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen; // Toggle the sidebar on mobile/tablet
    },
  },
};
</script>

<style>
.sidebar {
  display: none; /* Initially hide sidebar for small screens */
}

.sidebar.sidebar-open {
  display: block;
  position: static;
}

/* Always show the sidebar on larger screens */
@media (min-width: 992px) {
  .sidebar {
    display: block !important; /* Ensure sidebar is always visible on larger screens */
  }
}
</style>
