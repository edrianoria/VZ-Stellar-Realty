<template>
  <div class="container-fluid p-0" :class="{ 'sidebar-hidden': sidebarClose}">
    <div class="sidebar d-flex flex-column align-items-center" id="collapseOne">
      <div class="logo mt-3 mb-5">
        <img src="../assets/logo-bgw.png" alt="Website logo">
      </div>
  
      <ul class="nav flex-column" id="sidebar-nav">
        <li class="nav-item">
          <a class="nav-link has-dropdown collapsed" data-bs-toggle="collapse" data-bs-target="#property-menu" aria-expanded="false" aria-controls="property-menu">Property List</a>
          <ul id="property-menu" class="accordion-collapse collapse list-unstyled" :class="{'accordion-collapse': sidebarClose}" data-bs-parent="#sidebar-nav">
            <li class="nav-item">
              <a class="nav-link" href="">Properties</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="">Add Property</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="">Update Property</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="">Delete Property</a>
            </li>
          </ul>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Appointments</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Sales Agents</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Comission</a>
        </li>
      </ul>
    </div>
  
    <div class="header">
      <button class="menu-button" type="button" @click="toggleSidebar"><i class="bi bi-list"></i></button>
      <div class="profile float-end">
        <button type="button" id="user-menu">
          <img src="../assets/default.png" alt="User Profile">
        </button>
      </div>
    </div>
  
    <div class="main">
  
    </div>
  </div>
  </template>
  
  <script>
  
  export default {
    name: "Admin",
    data() {
      return {
        sidebarClose: true
      };
    },
    methods: {
      toggleSidebar() {
        this.sidebarClose = !this.sidebarClose;
      }
    }
  }
  </script>
  
  <style scoped>

  #property-menu .nav-link {
    font-size: 1.1rem !important;
  }

  .header .menu-button {
    border: none;
    background: transparent;
  }

  .header .menu-button .bi-list {
    font-size: 1.5rem;
  }

  .accordion-collapse {
    transition: height 0.3s ease;
  }

  .container-fluid {
    height: 100vh;
    display: grid;
    grid-template-columns: 300px 1fr;
    grid-template-rows: 60px 1fr;
    grid-template-areas: "side header" "side main";
    transition: grid-template-columns 0.3s ease;
  }

  .sidebar-hidden {
    grid-template-columns: 0 1fr !important;
    transition: grid-template-columns 0.3s ease;
  }
  
  .sidebar {
    background: #191a36;
    grid-area: side;
  }
  
  .sidebar .logo {
    width: 150px;
    height: 150px;
  }
  
  .logo img {
    width: 100%;
    height: 100%;
  }
  
  .nav {
    min-width: 100%;
    text-align: center;
  }
  
  .nav .nav-item {
    border-top: 1px solid rgba(84, 84, 84, 0.30);
    border-bottom: 1px solid rgba(84, 84, 84, 0.45);
  }
  
  .nav .nav-item a {
    font-size: 1.2rem;
    color: var(--vt-c-white);
  }
  
  .nav .nav-item a:hover {
    background: #2c3e50;
  }
  
  .header {
    background: white;
    grid-area: header;
  }
  
  .header .profile {
    width: 75px;
    height: 60px;
  }

  .header button {
    margin-top: 11px;
    margin-left: 10px;
  }
  
  .profile img {
    width: 100%;
    height: 100%;
  }
  
  .main {
    background: grey;
    grid-area: main;
  }

  #user-menu {
    border: none;
    margin: 0;
    padding: 0;
  }
  </style>