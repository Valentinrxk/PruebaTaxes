<template>
    <div class="layout-px-spacing">
      <div class="row layout-top-spacing" id="cancel-row">
        <div class="col-xl-12 col-lg-12 col-md-12">
          <div class="statbox panel box box-shadow">
            <div class="panel-body">
              <h2>Comienzo de la prueba</h2>
              <div v-if="loading" class="alert alert-info" role="alert">
                Cargando datos, por favor espere...
              </div>
              <div v-else class="table-responsive">
                <table role="table" aria-busy="false" aria-colcount="6" class="table table-hover table-bordered">
                  <thead role="rowgroup">
                    <tr role="row">
                      <th role="columnheader" scope="col" aria-colindex="1">
                        <div>ID</div>
                      </th>
                      <th role="columnheader" scope="col" aria-colindex="2">
                        <div>Title</div>
                      </th>
                      <th role="columnheader" scope="col" aria-colindex="3">
                        <div>Price</div>
                      </th>
                      <th role="columnheader" scope="col" aria-colindex="4">
                        <div>Category</div>
                      </th>
                      <th role="columnheader" scope="col" aria-colindex="5">
                        <div>Description</div>
                      </th>
                      <th role="columnheader" scope="col" aria-colindex="6" aria-label="Action" class="text-center">
                        <div>Action</div>
                      </th>
                    </tr>
                  </thead>
                  <tbody role="rowgroup">
                    <tr v-for="item in data" :key="item.id" role="row" :class="{'table-danger': item.price > 100}">
                      <td aria-colindex="1" role="cell">{{ item.id }}</td>
                      <td aria-colindex="2" role="cell">{{ item.title }}</td>
                      <td aria-colindex="3" role="cell">{{ item.price }}</td>
                      <td aria-colindex="4" role="cell">{{ item.category }}</td>
                      <td aria-colindex="5" role="cell">{{ item.description }}</td>
                      <td aria-colindex="6" role="cell" class="text-center">
                        <button @click="viewDetails(item)" class="btn btn-primary">Ver más</button>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import axios from 'axios';
  import { useRouter } from 'vue-router';
  
  const router = useRouter();
  const data = ref([]);
  const loading = ref(true);
  
  const fetchData = async () => {
    try {
      const response = await axios.get('https://fakestoreapi.com/products?limit=10');
      data.value = response.data;
    } catch (error) {
      console.error('Error fetching data:', error);
    } finally {
      loading.value = false;
    }
  };
  
  const viewDetails = (item) => {
    router.push({ name: 'ProductDetail', params: { id: item.id } });
  };
  
  onMounted(fetchData);
  </script>