<template>
 <div id="app-body">
   
   

    <div id="inputs">
         <input v-model="name" type="text" id="name" placeholder="Enter name...">
         <input  v-model="phone" type="number" id="phone" placeholder="Enter phone number..">
         <button id="save" v-on:click="saveToDirectory()">SAVE</button>

       
     </div>

    </div>

</template>

<script>


export default {
  name: 'Body',
  props: ['name','phone'],

  data: function(){
      return {
       
      }

  },
 
  methods: {
      saveToDirectory: function(){
           let name = this.name;

           let phone = this.phone;

        let person = { name, phone };

         
           this.$emit("saveTo", person);

           
      }



     
      }
}

     

    



  
 

</script>

<style>

#app-body {
    flex-grow: 1;
    overflow : hidden;
 
}
 
h3 {
    font-size: 25px;
    text-align: center;
    font-style: italic;
}

ol {
    margin-bottom: 5px;
}

.person {
    height: 200px;
 
}
#name, #phone, #save {
    width: 480px;
    padding: 6px;
    font-family: 'Dancing Script', cursive; 
    font-size: 18px;
    color: palevioletred;
    font-weight: bold;

}
#save {
    border-bottom-right-radius: 10px;
    border-bottom-left-radius: 10px ;
    width: 492px;
}


#app-body {
    position: relative;
    box-sizing: content-box;
    height: 25%;
}

</style>
