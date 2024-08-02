<template>
    <footer class="footer">
      <div class="footer-content">
        <div class="social-media">
          <a href="https://facebook.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-facebook-f"></i></a>
          <a href="https://twitter.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-twitter"></i></a>
          <a href="https://instagram.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-instagram"></i></a>
        </div>
        <div class="site-info">
          <p>&copy; 2024 eCommerce Site. All rights reserved.</p>
          <p><router-link to="/terms">Terms of Service</router-link> | <router-link to="/privacy">Privacy Policy</router-link></p>
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'Footer'
  }
  </script>
  
  <style scoped>
  .footer {
    background-color: #333;
    color: #fff;
    padding: 20px;
    text-align: center;
  }
  
  .footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }
  
  .social-media a {
    color: #fff;
    margin: 0 10px;
    text-decoration: none;
  }
  
  .social-media a:hover {
    color: #aaa;
  }
  
  .site-info p {
    margin: 5px 0;
  }
  
  .site-info a {
    color: #fff;
    text-decoration: none;
  }
  
  .site-info a:hover {
    text-decoration: underline;
  }
  </style>
  