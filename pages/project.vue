<template>
    <!--Have to do inline styling, otherwise it gets overwritten by the footer for some reason-->
    <div id="projects" style="flex-direction: row !important; flex-wrap: wrap !important; justify-content: flex-start !important;">
        <project :img-src="'/img/COS 216.png'" :title="'COS 216 Store Page'" :description="'A Store page website which interfaces with a mysql database using PHP to display product data.'" :language="['CSS', 'ECMAScript5', 'PHP', 'HTML']" />
        <project :img-src="'/img/INF 272.png'" :title="'INF 272 MVC Project'" :description="'A Razer MVC Project, that adds users to Browser storage, and displays static HTML pages of each user.'" :language="['CSS', 'Javascript', 'Razer', 'C#', 'Bootstrap']" />
        <project :img-src="'/img/IMY 210.png'" :title="'IMY 210 XML Edit'" :description="'A file upload site that allows users to upload xml files, which they can then edit and validate with their own files.'" :language="['CSS', 'Javascript', 'Vue', 'HTML']" />
    </div>
</template>

<script setup>
    import project from '~/components/project.vue';
</script>
<style scoped>
    @import './styles/projectPage.css';
</style>