<template>
  <div>
    <navbar />
  </div>
  <div id="content">
    <NuxtPage />
  </div>
  <div id="footer">
    <div>
      Random Fun Fact:
    </div>
    <div id="fact">
      Loading...
    </div>
  </div>
</template>

<script setup>
  import navbar from './components/navbar.vue';
  import {ref, onMounted} from 'vue';
  const fact = ref("");


  const getRandomFact = async() => {
    const response = await fetch("https://uselessfacts.jsph.pl/api/v2/facts/random");
    const data = await response.json();
    fact.value = data.text;
    };

  onMounted(async () => {
    await getRandomFact();
    document.getElementById("fact").innerHTML = fact.value;

  });
</script>


