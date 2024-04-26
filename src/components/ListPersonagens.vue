<script setup>
    const personagem = defineProps(["name", "url", "status", "species", "gender", "location", "image"])
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3 p-2">
            <img :src="personagem.image" class="card-img-top" height="100%" alt="...">
            <div class="card-body">
                <p class="card-title"><b>Nome:</b> {{ personagem.name }}</p>
                <p class="card-title"><b>Status:</b> {{ personagem.status }}</p>
                <p class="card-title"><b>Espécie:</b> {{ personagem.species }}</p>
                <p class="card-title"><b>Gênero:</b> {{ personagem.gender }}</p>
                <p class="card-title"><b>Localização Atual:</b> {{ personagem.location.name }}</p>
            </div>
        </div>
    </div>
</template>

<style>

</style>