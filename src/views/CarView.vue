<script setup>
    import { onBeforeMount, ref } from "vue";
import {useRoute} from "vue-router"
import cars from '../data.json'

    const car = ref(null)
    const route = useRoute()

    const {id} = route.params

    onBeforeMount(() => {
        car.value = cars.find(c => c.id === parseInt(id))
    })
</script>

<template>
    <div class="container">
        <h1>The Car</h1>
        <p>Make: {{ car.make }}</p>
        <p>Body: {{ car.body }}</p>
        <p>Price: {{ car.price }}</p>
        <p>Year: {{ car.year }}</p>
    </div>
</template>