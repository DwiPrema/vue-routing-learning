<script setup>
import { onBeforeMount, ref } from "vue";
import { useRoute, RouterView, useRouter } from "vue-router"
import cars from '../data.json'

const car = ref(null)
const route = useRoute()
const router = useRouter()

const { id } = route.params

onBeforeMount(() => {
    car.value = cars.find(c => c.id === parseInt(id))
})
</script>

<template>
    <div class="container">
        <div v-if="car">
            <h1>The Car</h1>
            <p>Make: {{ car.make }}</p>
            <p>Body: {{ car.body }}</p>
            <p>Price: {{ car.price }}</p>
            <p>Year: {{ car.year }}</p>
            <RouterView />
            <button @click="router.back()">Go Back</button>
        </div>

        <div v-else>
            <h1>Car Not Found!</h1>
        </div>
    </div>
</template>