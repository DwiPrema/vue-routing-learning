<script setup>
import { ref } from "vue";
import carsData from "../data.json";
import { useRouter } from "vue-router";

const router = useRouter()

const cars = ref(carsData)
</script>

<template>
    <main class="container">
        <h1>Our Cars</h1>
        <div class="cards">
            <div @click="router.push(`/car/${car.id}`)" v-for="car in cars" :key="car.id" class="card">
                <h1>{{ car.make }}</h1>
                <p>${{ car.price }}</p>
            </div>
        </div>
    </main>
</template>

<style scoped>
.cards {
    display: flex;
    width: 1000px;
    flex-wrap: wrap;
    margin-top: 50px;
    justify-content: center;
}

.card {
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.207);
    padding: 15px;
    width: 150px;
    margin-right: 15px;
    cursor: pointer;
    margin-bottom: 20px;

}
</style>
