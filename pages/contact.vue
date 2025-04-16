<template>
    <div>
        <div id="title">
            CONTACT US
        </div>
        <div id="subtitle">
            I have no idea who uses this part of the website, but it exists!<br>
            Also theres a comic on the side if you want to see today's XKCD comic
        </div>
    </div>
    <div id="body">
        <div>
            <form name="contact" method="POST" netlify id="contact-form">
                <div>
                    <label for="name">Your Name:</label>
                    <input type="text" name="name" id="name" />
                </div>
                <div>
                    <label for="email">Email:</label>
                    <input type="text" name="email" id="email" />
                </div>
                <div>
                    <label for="subject">Subject:</label>
                    <input type="text" name="subject" id="subject" />
                </div>
                <div>
                    <label for="message">Message:</label>
                    <textarea name="message" id="message" style="resize:none"></textarea>
                </div>
                <div>
                    <button type="submit">Send</button>
                </div>
            </form>
        </div>
        <div id="comic">
            <div id="comic-title">Todays Comic: </div>
            <div id="comic-name">Loading...</div>
            <img :src="comic.img" alt="Loading...">
        </div>
    </div>
</template>

<style scoped>
    @import '../styles/contact.css';
</style>

<script setup>
  import {ref, onMounted} from 'vue';
  const comic = ref("");


    const getRandomFact = async() => {
    const response = await fetch("https://xkcd.now.sh/?comic=latest");
    const data = await response.json();
    comic.value = data;
    };

  onMounted(async () => {
    await getRandomFact();
    document.getElementById("comic-name").innerHTML = comic.value.safe_title;

  });
</script>