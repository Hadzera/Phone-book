<template>
    <div id="persons">

        
    
       
   <p>Name and number:</p>
       
  
    <div v-for="(person, id) in persons" v-bind:key="id" >


      <ul>

        <li>
         
          {{person.name}} {{person.phone}}

          <button id="delete" v-on:click="remove(id)">x</button>

        </li>

      </ul>

    </div> 
    </div>
</template>

<script>
export default {
    name: 'Delete',
    props: ['name', 'phone', 'persons'],
   
    data: function(){
       return {
        
      
        
       } 
    },
    methods: {
        remove: function(id) {


      this.$emit("removePerson", id);

    }
    
    
    
    
        
    }

      
        
    }

  


</script>

<style scoped>

#persons {

  height: 75%;
  background-color: rgba(240, 128, 128, 0.205);
}

p {
  text-align: center;
  font-size: 22px;
  
  
}

#delete {
  height: 5px;
  width: 2px;
  font-size: 10px;
  padding-bottom: 13px;
  padding-right: 10px;
  border-radius: 10px;
  background-color: palevioletred;
  color: white;
}

</style>