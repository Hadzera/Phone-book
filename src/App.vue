<template>
 <div id="app-container">
   <div id="header">
      <h3>
       *YOUR PHONE DIRECTORY*
     </h3>
   </div>
    
  
    
   
  <delete-person :persons="listOfPersons" @removePerson="onDelete" ></delete-person> 
  <add-person @saveTo="savePerson"></add-person>
 </div>

</template>

<script>


import Delete from './components/Delete'
import Body from './components/Body'





const STORAGE_KEY = 'person-storage';
export default {
  name: 'App',
  components: {
    'delete-person': Delete,
    'add-person': Body
    
     },
     data: function(){
       return {

      listOfPersons: []
     }

     },
     created () {
        this.listOfPersons = JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]')
     },

  methods: {
     onDelete: function(id){
       this.listOfPersons.splice(id, 1);
       
       localStorage.setItem(STORAGE_KEY, JSON.stringify(this.listOfPersons))
      
     },
     savePerson: function(person){
     this.listOfPersons.push(person); 
     
      localStorage.setItem(STORAGE_KEY, JSON.stringify(this.listOfPersons))
    
     
      

     },

    

  
    
          

       
     },

}

     
    

     
    
   
     
     
    
     

     
   
    
     
       
          
    
    
     


  
 

</script>

<style>

body {
    background : linear-gradient(45deg, #215db6, #C5796D);
    height     : 100vh;
    margin     : 0;
    box-sizing : border-box;
    font-family: sans-serif;
    color: palevioletred;
    font-family: 'Dancing Script', cursive;
}

#app-container {
    max-width    : 490px;
    margin       : 0 auto;
    height       : 95vh;
    background   : white;
    box-shadow   : 0 5px 9px rgba(0, 0, 0, 0.16),
        0 3px 6px rgba(0, 0, 0, 0.23);
    transform     : translate(0, -50%);
    top           : 50%;
    position      : relative;
    border-radius: 10px;
  
}

h3 {
  padding-top: 10px;
}



</style>
