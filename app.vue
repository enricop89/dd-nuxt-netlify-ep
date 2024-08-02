<template>
  <div>
    
    <Header />

    <main>
      <section class="hero">
        <div class="hero-content">
          <h1>Welcome to Our eCommerce Store</h1>
          <p>Discover our amazing products!</p>
        </div>
      </section>

      <section class="products">
        <h2>Our Products</h2>
        <div class="product-list">
          <div class="product" v-for="product in products" :key="product.id">
            <img :src="product.image" :alt="product.name">
            <h3>{{ product.name }}</h3>
            <p>{{ product.description }}</p>
            <p class="price">{{ product.price }}</p>
            <button @click="addToCart(product)">Add to Cart</button>
          </div>
        </div>
      </section>
    </main>

    <Footer />
  </div>
</template>

<script>
import Header from './app/components/Header.vue'
import Footer from './app/components/Footer.vue'

import { datadogRum } from '@datadog/browser-rum';

datadogRum.init({
    applicationId: '79fe91c2-9e2d-4998-9d91-e4720239eaff',
    clientToken: 'pub66965ec69c5f9d16a0371fac77f24857',
    // `site` refers to the Datadog site parameter of your organization
    // see https://docs.datadoghq.com/getting_started/site/
    site: 'datadoghq.com',
    service: 'nutxtjs-store-enrico',
    env: 'prod',
    // Specify a version number to identify the deployed version of your application in Datadog
    // version: '1.0.0', 
    sessionSampleRate: 100,
    sessionReplaySampleRate: 20,
    trackUserInteractions: true,
    trackResources: true,
    trackLongTasks: true,
    defaultPrivacyLevel: 'mask-user-input',
});

export default {
  name: 'App',
  components: {
    Header,
    Footer
  },
  data() {
    return {
      products: [
        {
          id: 1,
          name: 'Product 1',
          description: 'Description for product 1',
          price: '$10.00',
          image: 'path/to/image1.jpg'
        },
        {
          id: 2,
          name: 'Product 2',
          description: 'Description for product 2',
          price: '$20.00',
          image: 'path/to/image2.jpg'
        },
        {
          id: 3,
          name: 'Product 3',
          description: 'Description for product 3',
          price: '$30.00',
          image: 'path/to/image3.jpg'
        },
        {
          id: 4,
          name: 'Product 4',
          description: 'Description for product 4',
          price: '$40.00',
          image: 'path/to/image4.jpg'
        }
      ]
    }
  },
  methods: {
    addToCart(product) {
      // Implement your add to cart functionality here
      console.log(`${product.name} added to cart!`);
    }
  }
}
</script>

<style scoped>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header, footer {
  background-color: #333;
  color: #fff;
  padding: 10px 20px;
  text-align: center;
}

.hero {
  background: url('path/to/hero-image.jpg') no-repeat center center/cover;
  color: #fff;
  text-align: center;
  padding: 50px 20px;
}

.hero-content {
  background-color: rgba(0, 0, 0, 0.5);
  display: inline-block;
  padding: 20px;
}

.products {
  padding: 20px;
}

.product-list {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.product {
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px;
  margin: 10px;
  text-align: center;
  width: 200px;
}

.product img {
  width: 100%;
  height: auto;
  border-bottom: 1px solid #ddd;
  padding-bottom: 10px;
}

.product h3 {
  font-size: 1.2em;
  margin: 10px 0;
}

.product .price {
  color: #28a745;
  font-size: 1.1em;
  margin: 10px 0;
}

.product button {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 10px;
  cursor: pointer;
  border-radius: 5px;
}

.product button:hover {
  background-color: #0056b3;
}
</style>
