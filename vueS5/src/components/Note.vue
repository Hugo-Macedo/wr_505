<script setup>
import { ref, computed } from 'vue'

const note1 = 15
const note2 = 18
const note3 = 10
const moyenne = (note1 + note2 + note3) / 3
const items = ref([{ message: 'première valeur' }, { message: 'deuxième message' }])

const somme = computed(() => {
    return note1 + note2 + note3
})


</script>

<template>
    <p>voici les 3 notes : {{ note1 }}, {{ note2 }}, {{ note3 }}<br> ainsi que la moyenne : {{ moyenne }}<br> ainsi que la
        somme : {{ somme }}</p>
    <li v-for="item in items">
        <p> {{ item.message }}</p>
    </li>
</template>