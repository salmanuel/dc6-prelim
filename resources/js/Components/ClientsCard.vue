<template>
    <div class="bg-gray-200 rounded shadow drop-shadow-lg p-4">
    <div class="flex justify-center">
        <img src="https://static-00.iconduck.com/assets.00/person-icon-1901x2048-a9h70k71.png" alt="Client Image" class="max-w-sm max-h-36">
    </div>
    <div class="text-center mt-2">
        <h3 class="font-semibold text-lg">{{ client.last_name }}, {{ client.first_name }}</h3>
        <p class="text-gray-600">{{ client.address }}</p>
    </div>
    </div>
</template>

<script setup>
const props = defineProps({
    client: Object
});
</script>
