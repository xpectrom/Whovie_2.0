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
      <h1>Send us the photo</h1>
      <!--Creates a new module to work in-->
      <div name="but" id="but">
        <button type = "button" id = "create_form" @click = "post_img">Let's Search</button>
      </div>
    <div id="imgId"></div>

  </div>
    </body>
</template>

<script stetup>
import axios from 'axios';

export default {
  data(){
    return{
        baseURL: 'http://127.0.0.1:8000',
      }
    },
  
  methods:{

      sendPost(image){

        console.log(image);

        axios
        .get(this.baseURL+'/files').then((response) => {
         console.log("This",response);
         });

      },

      post_img(){
        
        var branch = document.getElementById("but");
        
        var but = document.getElementById("create_form");
        
        branch.removeChild(but);
        
        var form = document.createElement("form");
        
        form.setAttribute("method", "post");

        var inp = document.createElement("input");

        inp.setAttribute("type", "file");

        inp.setAttribute("id", "img");

        inp.setAttribute("name", "img");

        inp.setAttribute("accept", "image");

        form.append(inp);

        var call = document.getElementById("imgId");

        call.appendChild(form);

        var sub = document.createElement("button");

        sub.setAttribute("type", "button");

        sub.setAttribute("id", "poster");

        sub.setAttribute("name", "poster");

        sub.textContent = 'Send Photo';

        var img = document.getElementById("img").value;

        sub.onclick = this.sendPost(img);

        call.appendChild(sub);

      }

  }

}

</script>
