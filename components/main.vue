<template>
    <head>
         <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vue.JS API Call</title>
    </head>
    <body>
    <div id="main" align="center">
      <div id = "connect"></div>
      <br/>
      <h1>Hello world</h1>
      <!--Creates a new module to work in-->
    <form mtehod="post">
    <label for="img">Select image:</label>
    <input type="file" id="img" name="img" accept="image/*">

    </form>
        <button type = "button" id = "call-scrap" @click = "config">Config</button>
    <div id="imgId"></div>

  </div>
    </body>
</template>

<script stetup>
import axios from 'axios';

export default {
  data(){
    return{

        }
    },
  
  methods:{

      post_img(){
        

      }

  }
}

</script>
