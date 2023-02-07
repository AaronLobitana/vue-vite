<template>
  <h1>{{ msg }}</h1>

<div class="topbuttons">
  <button class="dupe" v-on:click="duplicate">Duplicate</button>
  <button class="changebg" v-on:click="background">Change Background</button>
  <button class="changehg" v-on:click="heading">Change Heading</button>
  <button class="del" id="del" v-on:click="deletecard">Delete</button>
</div>

<div class="overallcard">
  <div class="box">
    
    <img class="pic" src="https://pbs.twimg.com/media/FajpQj_XwAEwCWw.jpg">
    
    <div class="heading">
      <h1>the brim reaper</h1>
    </div>
    
    <div class="details">
      <h3>fear the reaper</h3>
    </div>
    <div class="reveal">
      <button class="detailsbutton">Details</button>
    </div>
 
 </div>

</div>
  
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<script>
export default {
  methods: {
    duplicate()
    {
      const copy = document.querySelector('.overallcard').cloneNode(true);
      document.body.appendChild(copy);
    },

    background()
    {
      const mybackground = document.querySelectorAll('.box');
        for (var i = 0; i < mybackground.length; i++)
        {
          if (mybackground[i].style.backgroundColor === "white")
          {
            mybackground[i].style.backgroundColor = "#B19CD9";
          }
          else
          {
            mybackground[i].style.backgroundColor = "white";
          }
        }
    },

    heading()
    {
      const myheading = document.querySelectorAll('.heading h1').forEach((item) => {
        if (item.innerHTML=="something else"){
          item.innerHTML="the brim reaper";
        }
        else{
          item.innerHTML="something else";
        }
      });

    },

    deletecard()
    {
      const lastElementIndex = document.querySelectorAll(".overallcard").length - 1;
      document.querySelectorAll(".overallcard").forEach((item, index) => {
      if (index === lastElementIndex) 
      {
        document.body.removeChild(item);
      }
      });
    }




   
  }
}
</script>


<style scoped>
a {
  color: #42b983;
}

.overallcard{
  width: 400px;
  border: 4px solid black;
  display: inline-flex;
}

.box{
  background-color: #B19CD9;
}

.pic{
  width: 400px;
  transition: transform .5s ease-in-out;
}

.pic:hover{
  transform: rotate(360deg);
}

.heading{
  text-align: center;
}

.details{
  text-align: center;
  display: none;
}

.topbuttons{
  margin: 10px 0px 10px 0px;
  display: block;
}


.dupe{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.changebg{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.changehg{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.del{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
}

.detailsbutton{
  background-color: #B19CD9;
  color: white;
  text-align: center;
  padding: 15px;
  transition: background-color 0.8s;
  border: 4px double white;
  font-size: 20px;
  margin: 10px;
}

.detailsbutton:hover{
  background-color: black;
}

.detailsbutton:focus{
  background: gray;
  color: #041E42;
}

.reveal{
  text-align: center;
}


.dupe:hover{
  background-color: black;
}

.dupe:focus{
  background: gray;
  color: #041E42;
}

.changebg:hover{
  background-color: black;
}

.changebg:focus{
  background: gray;
  color: #041E42;
}

.changehg:hover{
  background-color: black;
}

.changehg:focus{
  background: gray;
  color: #041E42;
}

.del:hover{
  background-color: black;
}

.del:focus{
  background: gray;
  color: #041E42;
}

@media only screen and (max-width: 425px)
{
  .reveal{
    display: none;
  }

  .overallcard{
    width: 250px;
    border: 4px solid black;
    display: inline-flex;
  }
  
  .pic{
    width: 250px;
    transition: transform .5s ease-in-out;
  }
}

</style>
