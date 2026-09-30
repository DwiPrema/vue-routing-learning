<script setup>
import { computed, onMounted, ref, watch } from "vue";
import carsData from "../data.json";
import { useRouter, useRoute } from "vue-router";

const router = useRouter()
const route = useRoute()

const cars = ref(carsData)

const filteredCars = ref(carsData)
const selectedMake = ref("All")

onMounted(() => {
    selectedMake.value = route.query.make
})

const uniqueMakes = computed(() => {
    return [...new Set(cars.value.map(car => car.make))]
})

watch(selectedMake, () => {
    if(selectedMake.value) {
        if(selectedMake.value === "All") return filteredCars.value = carsData;
        else {
            filteredCars.value = carsData.filter(c => c.make ===selectedMake.value)
        }
    }
})

const handleChange = () => {
    router.push({
        query: {
            make: selectedMake.value
        }
    })
}
</script>

<template>
    <main class="container">
        <h1>Our Cars</h1>
        <select @change="handleChange" v-model="selectedMake">
            <option value="All">All</option>
            <option v-for="make in uniqueMakes" :value="make">{{ make }}</option>
        </select>
        <div class="cards">
            <div @click="router.push(`/car/${car.id}`)" v-for="car in filteredCars" :key="car.id" class="card">
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
