<script setup>
// props - onMounted, reactive, ref
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';



let personagens = reactive(ref())

// fetch - axios
onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(response => {
      personagens.value = response.results
      console.log(personagens)
    });
})


</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-12">
          <div class="card">
            <div class="card-body row">
              <ListPersonagens v-for="personagem in personagens" :key="personagem.name" :name="personagem.name" :url="personagem.url" :status="personagem.status" :species="personagem.species" :gender="personagem.gender" :location="personagem.location" :image="personagem.image"/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
