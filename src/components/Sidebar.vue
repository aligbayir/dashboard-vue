<template>
    <nav class="sidebar">
      <div class="sidebar-header">
        <h3 class="baslik">Dashboard</h3>
      </div>
      <ul class="list-unstyled components">
        <li>
          <router-link class="side-link" :to="{name:'home'}">
            <i class="fas fa-home"></i>
            Müşteri İşlemleri
            <i @click="openSubMenu" class="fa-solid fa-circle-chevron-down distance"></i>
          </router-link>
          <ul v-if="isOpen">
            <li>
              <router-link :to="{name:'home'}" class="side-link">Cari İşlemler</router-link>
            </li>
          </ul>
        </li>
        <li>
          <a href="#usersSubmenu" data-toggle="collapse" aria-expanded="false" class="dropdown-toggle side-link">
            <i class="fas fa-users"></i>
            Users
          </a>
        </li>
        <li>
          <router-link class="side-link" to="#">
            <i class="fas fa-chart-bar"></i>
            Analytics
          </router-link>
        </li>
        <li>
          <router-link class="side-link" to="#">
            <i class="fas fa-cog"></i>
            Settings
          </router-link>
        </li>
      </ul>
    </nav>
  </template>
<script>
import {ref} from 'vue'

export default {
    setup() {
      const isOpen =ref(false);

      const openSubMenu= ()=>{
        isOpen = !isOpen
      }

      return {isOpen,openSubMenu};
    }
}
</script>
<style>
    .sidebar {
    background: #f8f9fa;
    padding: 10px;
    width: 250px;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;
    overflow-x: hidden;
  }

  .sidebar-header {
    padding: 20px;
    background: #e7e4e4;
    border-bottom: 2px solid #dee2e6;
  }
  .sidebar-header h3 {
    text-align: center;
  }

  .sidebar ul.components {
    padding: 20px 0;
    border-bottom: 1px solid #dee2e6;
  }

  .sidebar ul p {
    color: #fff;
    padding: 10px;
  }

  .sidebar ul li a {
    padding: 10px;
    font-size: 1.1em;
    display: block;
  }

  .sidebar ul li a i {
    margin-right: 10px;
  }

  .sidebar ul li.active > a,
  .sidebar ul li a:hover {
    background: #17a2b8;
    color: #fff;
  }

  .sidebar ul li ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .sidebar ul li ul li a {
    font-size: 0.9em;
    padding: 10px;
    display: block;
  }

  .sidebar ul li ul li a:hover {
    background: #5e6b7f;
  }
  .side-link {
    color: #7a7272;
    text-decoration: none;
    margin-top: 10px;
  }
  .distance {
    margin-left:60px;
  }
</style>