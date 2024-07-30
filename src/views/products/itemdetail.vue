<template>
  <div v-if="product" class="card">
    <img :src="product.image" class="card-img-top" alt="product image" style="max-width:200px; height: auto;">
    <div class="card-body">
      <h5 class="card-title">{{ product.title }}</h5>
      <p class="card-text">{{ product.description }}</p>
      <p class="card-text"><strong>Price:</strong> ${{ product.price }}</p>
      <p v-if="product.rating" class="card-text">
        <strong>Rating:</strong> {{ product.rating.rate }} ({{ product.rating.count }} reviews)
      </p>
      <p v-else class="card-text">
        <strong>Rating:</strong> Not available
      </p>
      <p v-if="product.stock" class="card-text">
        <strong>Stock:</strong> {{ product.stock }}
      </p>
      <p v-else class="card-text">
        <strong>Stock:</strong> Not available
      </p>
    </div>
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useRoute } from 'vue-router';
import axios from 'axios';

const route = useRoute();
const product = ref(null);

const fetchProduct = async () => {
  const id = route.params.id;
  try {
    const response = await axios.get(`https://fakestoreapi.com/products/${id}`);
    product.value = response.data;
  } catch (error) {
    console.error('Error fetching product details:', error);
  }
};

onMounted(fetchProduct);
</script>