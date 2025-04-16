<template>
    <div class="indivProject">
        <div>
            <img :src="imgSrc" width="512" height="270">
        </div>
        <div>
            <div id="title">
                {{ title }}
            </div>
            <div id="description">
                {{ description }}
            </div>
            <hr>
            <div id="languages">
                <div id="languageTitle">Languages</div>
                <ul style="list-style-type: none;">
                    <li v-for="language in language">
                        {{ language }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
    defineProps({
        imgSrc: String,
        title: String,
        description: String,
        language: Array
    })
</script>

<style scoped>
    @import '../styles/project.css';
</style>