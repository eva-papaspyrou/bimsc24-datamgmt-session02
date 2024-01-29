<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()
const SpeciesName = ["Abelia floribunda", "Abelia triflora", "Abelia umbellata", "Abelia x Edward Goucher", "Abelia x grandiflora", "Abies alba", "Abies balsamea"]
let extraname = ref("generate species")
let selectedSpecies = ref("");
function PickRandomSpecies() {
const randomIndex = Math.floor(Math.random() * SpeciesName.length);
selectedSpecies.value = SpeciesName[randomIndex]; 
}
</script> 



<!-- the template is where the html code goes -->
<template>

<div id="navbar" class="container"></div>

<div id="flex">
    <div id="empty" class="container"></div>
    <div id="main" class="container"> <!--{{ extraname }} // title without button function--> 
<button @click="PickRandomSpecies">{{ extraname }}</button>
<p>{{ selectedSpecies }}</p>
        <div id="video-container">
            <video controls 
            width="1120" 
            height="630"
            autoplay
            loop
            >
                <source src="https://cdn-luma.com/69340914fb394511ff09152f1a3d77041b1354ce75151412ab93b41e7d208c7e.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>
    <div id="sidebar" class="container">

        <div id="text1" class="sidebar-item">
            <p>plant type</p>
        </div>
        <div id="text2" class="sidebar-item">
            <p>native country</p>
        </div>
        <div id="text3" class="sidebar-item">
            <p>water needs</p>
        </div>
    </div>
</div>

</template>



<!-- style is where the css code goes -->
<style scoped>

/* VIDEO */
/* size */
#video-container {
    position: fixed; /* Use fixed positioning to cover the entire viewport */
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1; /* Set a negative z-index to place it behind other elements */
}

#video-container video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0.6;
}
/* Disable native controls in WebKit browsers */
#video-container video::-webkit-media-controls {
    display: none !important; 
}

html {
    background-color: rgb(241, 241, 241);
    color: rgb(255, 255, 255);
    font-family: Helvetica, sans-serif;
    font-weight: bold;
    font-size: 27px;
}

body {
    background-image: url('https://raw.githubusercontent.com/jose-villegas/HeightmapGenerator/master/HeightmapGenerator/Resources/perlin_1.BMP');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    margin: 0;
}

div {
    box-sizing: border-box;
}

#navbar {
    height: 100px;
}

#flex {
    display: flex;
    height: calc(100vh - 100px);
}
#empty{
    width: 15%;
}
#main {
  width: 75%;
 /* position: relative;
  z-index: 1;
  color: white;
  font-family: Helvetica, sans-serif;
  font-size: 27px;
  font-weight: bold; */ /*for title without button */
}
#main button {
  color: white; /* Set text color to white */
  font-family: Helvetica, sans-serif; /* Set font-family to Helvetica */
  font-size: 50px;
  font-weight: bold;
  background-color: transparent; /* Make the button background transparent */
  border: none; /* Remove the button border */
  cursor: pointer; /* Change cursor on hover to indicate interactivity */
  padding: 10px 20px; /* Add padding for better styling */
}

#main button:hover {
  background-color: rgba(255, 255, 255, 0.2); /* Add a subtle background color on hover */
}
/* VIDEO */
/* size */
#sidebar {
    width: 15%;
    display: flex;
    flex-direction: column;
    justify-content: left;
    align-items: center;
    z-index: 1; /* Set a higher z-index to place it in front of the video */
    margin-top: 50px; 
}

.sidebar-item {

    margin-bottom: 200px;
}

.sidebar-item p {
    transform: rotate(90deg);
    white-space: nowrap;
    overflow: hidden;
    transform-origin: center;
    color: white; /* Set text color to white */
  font-family: Helvetica, sans-serif; /* Set font-family to Helvetica */
  font-size: 27px;
  font-weight: bold;
}



/* .container {
    border-color: rgb(60, 255, 0);
    border-style: dotted;
    border-width: 1px;
} */

</style>