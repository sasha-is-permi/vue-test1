<template>
    <div class="libraryes">
        <p> Фильтр: </p>
        <input type="text" v-model="librarySearch"/>
        <p class="library"  v-for="library in libraryes" :key="library._id">
        <router-link 
        :to="{name:'Library' ,params:{library:library}}"    
        >   {{library.data.general.name}}  </router-link>
        </p>   
    </div>
</template>


<script>
   export default{
       data() {
         return{
           librarySearch:""    
         }
       },
           
              computed: {           
              libraryes() {
                  let libraryes2 = this.$store.getters.libraryes;
                  console.log("libraryes", libraryes2)
                
                  libraryes2 = libraryes2.filter(item => {
                  return item.data.general.name.toUpperCase().indexOf(this.librarySearch.toUpperCase())!==-1;
                    })

                  console.log("libraryes2", libraryes2)
                    return libraryes2;
            }
            }
                
                }

                
            

 

</script>

<style scoped>

</style>