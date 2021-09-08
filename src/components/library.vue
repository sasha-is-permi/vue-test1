<template>
<div>
   <h2> {{name}}</h2>
   <p><span v-html="description"></span></p>
   <p>Адрес: {{ adress}}</p>
   <p>сайт: <a :href="websait" target="_new">{{ websait }}</a></p>
   <p>email: <a :href="'mailto:'+email"> {{ email }}</a>  </p>
   <p>телефон: <a :href="'tel:'+tel"> {{ tel }}</a>  </p>
    <p> <img class="img" :src="img"/> </p>
    <div>
     <router-link class="red" to="/List">  Вернуться к списку библиотек   </router-link> 
    </div> 
 </div>   
</template>

<script>
export default{
 data(){   
 return{
 name:     this.$route.params.library.data.general.name || " " ,
 description: this.$route.params.library.data.general.description || " ",
 adress:  this.$route.params.library.data.general.address.street || " ", 
 websait:  this.$route.params.library.data.general.contacts.website || " " ,
 library: this.$route.params.library || " ",
 email: this.$route.params.library.data.general.contacts.email || " ",
 tel: this.$route.params.library.data.general.contacts.phones[0].value || " " ,
 img: this.$route.params.library.data.general.image.url || " " 
 }
 }
}
</script>

<style scoped>

.red{
    color:#c00;
}

.img{
    width:300px;
}

</style>