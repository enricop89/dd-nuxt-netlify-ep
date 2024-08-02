<template>
    <header class="header">
      <div class="logo">
        <h1>eCommerce Site</h1>
      </div>
      <nav class="nav">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/shop">Shop</router-link></li>
          <li><router-link to="/about">About Us</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </nav>
      <div class="cart">
        <router-link to="/cart">
          <i class="fas fa-shopping-cart"></i>
          <span>Cart ({{ cartItemCount }})</span>
        </router-link>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
    computed: {
      cartItemCount() {
        // Assuming you have a Vuex store and cart module
        return 2;
      }
    }
  }
  </script>
  
  <style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    background-color: #333;
    color: #fff;
  }
  
  .logo {
    display: flex;
    align-items: center;
  }
  
  .logo img {
    height: 40px;
    margin-right: 10px;
  }
  
  .nav ul {
    list-style: none;
    display: flex;
    margin: 0;
    padding: 0;
  }
  
  .nav ul li {
    margin: 0 10px;
  }
  
  .nav ul li a {
    color: #fff;
    text-decoration: none;
  }
  
  .nav ul li a:hover {
    text-decoration: underline;
  }
  
  .cart {
    display: flex;
    align-items: center;
  }
  
  .cart i {
    font-size: 1.2em;
    margin-right: 5px;
  }
  </style>
  