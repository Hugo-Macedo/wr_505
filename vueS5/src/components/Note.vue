<script setup>
import { ref, computed } from 'vue'

const note1 = 9
const note2 = 18
const note3 = 10
const note4 = 0
const note5 = 3
const moyenne = (note1 + note2 + note3) / 3
const items = ref([{ message: 'première valeur' }, { message: 'deuxième message' }])

const somme = computed(() => {
    return note1 + note2 + note3
})
const awesome = ref(true)
const notes = ref([{ note: '11' }, { note: '8' }, { note: '15' }, { note: '11' }, { note: '12' }, { note: '14' }, { note: '8' }, { note: '5' }, { note: '1' }, { note: '18' }])

</script>

<template>
    <p>voici les 3 notes : {{ note1 }}, {{ note2 }}, {{ note3 }}<br> ainsi que la moyenne : {{ moyenne }}<br> ainsi que la
        somme : {{ somme }}</p>
    <li v-for="item in items">
        <p> {{ item.message }}</p>
    </li>

    <button @click="awesome = !awesome">Basculer</button>
    <h1 v-if="awesome">Vue est magnifique!</h1>
    <h1 v-else>Oh non 😢</h1>

    <div v-if=8>{{ note1 }} >10>
        <p> la note1 est comprise entre 8 et 10</p>
    </div>
    <div v-else-if=note2>10>
        <p> la note2 est supérieur à 10</p>
    </div>
    <div v-else-if="note3 > 10">
        <p> la note3 est supérieur à 10</p>
    </div>
    <div v-else-if="note4 > 10">
        <p> la note4 est supérieur à 10</p>
    </div>
    <div v-else-if="note5 > 10">
        <p> la note5 est supérieur à 10</p>
    </div>

    <li v-for="(value, index) in  notes" style = 'list-style-type: none;'>
        <span v-if = "value.note>10">
            {{ index }}
            <ul style='color:green; list-style-type: none;'>{{ value.note }}</ul>
        </span>
        <span v-else>
            {{ index }}
            <ul style= 'color:red; list-style-type: none;'>{{ value.note }}</ul>
        </span>
    </li>
</template>