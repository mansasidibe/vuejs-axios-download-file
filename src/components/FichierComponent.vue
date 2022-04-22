<template>
  <div id="app">

         <nav class="navbar background">
        <ul class="nav-list">
            <li><a href="#web">Web</a></li>
            <li><a href="#program">Mobile</a></li>
        </ul>
 
        <div class="rightNav">
            <input type="text" name="search" id="search">
            <button class="btn btn-sm">Recherche...</button>
        </div>
    </nav>
 
    <section class="section">
        <div class="paras">
            <h2>Télécharger un fichier en Vue Js avec Axios</h2> <br>
 
            <p class="sectionSubTag text-small">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae dolorem 
                maiores error sequi aperiam! Dignissimos aliquid ut illo ab vitae explicabo 
                accusantium cumque facere nisi. Eligendi excepturi fuga voluptatem inventore.
            </p>
 
 
        </div>
 
        <div class="thumbnail">
            <button v-on:click="downloadFile()">Télécharger</button>
        </div>
    </section>
      
      
  </div>
</template>
 
   
<script>
    import axios from 'axios';
    
    export default {
      mounted() {
          this.downloadFile();
      },
      methods: {
          downloadFile() {
              axios({
                    url: 'https://riptutorial.com/Download/laravel-fr.pdf', // Mettre le lien URL du fichier à télécharger
                    method: 'GET',
                    responseType: 'blob',
                }).then((res) => {
                     var FILE = window.URL.createObjectURL(new Blob([res.data]));
                     
                     var docUrl = document.createElement('x');
                     docUrl.href = FILE;
                     docUrl.setAttribute('download', 'file.pdf');
                     document.body.appendChild(docUrl);
                     docUrl.click();
                });
          }
      }
    }
</script>

<style scoped>
 * {
        margin: 0;
        padding: 0;
    }
 
    .navbar {
        display: flex;
        align-items: center;
        justify-content: center;
        position: sticky;
        top: 0;
        cursor: pointer;
    }
 
    .background {
        background: black;
        background-blend-mode: darken;
        background-size: cover;
    }
 
    .nav-list {
        width: 70%;
        display: flex;
        align-items: center;
    }
 
    .logo {
        display: flex;
        justify-content: center;
        align-items: center;
    }
 
    .logo img {
        width: 180px;
        border-radius: 50px;
    }
 
    .nav-list li {
        list-style: none;
        padding: 26px 30px;
    }
 
    .nav-list li a {
        text-decoration: none;
        color: white;
    }
 
    .nav-list li a:hover {
        color: grey;
    }
 
    .rightnav {
        width: 30%;
        text-align: right;
    }
 
    #search {
        padding: 5px;
        font-size: 17px;
        border: 2px solid grey;
        border-radius: 9px;
    }
 
    .firstsection {
        background-color: green;
        height: 400px;
    }
 
    .secondsection {
        background-color: blue;
        height: 400px;
    }
 
    .box-main {
        display: flex;
        justify-content: center;
        align-items: center;
        color: black;
        max-width: 80%;
        margin: auto;
        height: 80%;
    }
 
    .firsthalf {
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
 
    .secondhalf {
        width: 30%;
    }
 
    .secondhalf img {
        width: 70%;
        border: 4px solid white;
        border-radius: 150px;
        display: block;
        margin: auto;
    }
 
    .text-big {
        font-family: 'Piazzolla', serif;
        font-weight: bold;
        font-size: 35px;
    }
 
    .text-small {
        font-size: 18px;
    }
 
    .btn {
        padding: 8px 20px;
        margin: 7px 0;
        border: 2px solid white;
        border-radius: 8px;
        background: none;
        color: white;
        cursor: pointer;
    }
 
    .btn-sm {
        padding: 6px 10px;
        vertical-align: middle;
    }
 
    .section {
        height: 400px;
        display: flex;
        align-items: center;
        justify-content: center;
        max-width: 90%;
        margin: auto;
    }
 
    .section-Left {
        flex-direction: row-reverse;
    }
 
    .paras {
        padding: 0px 65px;
    }
 
    .thumbnail img {
        width: 250px;
        border: 2px solid black;
        border-radius: 26px;
        margin-top: 19px;
    }
 
    .center {
        text-align: center;
    }
 
    .text-footer {
        text-align: center;
        padding: 30px 0;
        font-family: 'Ubuntu', sans-serif;
        display: flex;
        justify-content: center;
        color: white;
    }
</style>