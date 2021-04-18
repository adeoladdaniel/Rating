<template>
  <div class="side-bar">
    <div class="logo-sec">
        <img class="logo" src="../assets/logo.png"  />

        <span> FEEDBACK APP</span>
    </div>
    <div class="user-sec">

       <img  class="round" src="../assets/user.jpeg" /> 

       <span> Adeola Daniel</span> 
    </div>
   
   <div class="team">
      <h7>
        Your Team mates
      </h7>

      <div class="user-sec" v-for="(user, ind) in users" :key="ind">

       <img  class="round" v-bind:src="require(`@/assets/${user.img}`) || '' " /> 

       <span>{{user.name}}</span> 
    </div>
     <!-- <div class="user-sec">

       <img  class="round" src="../assets/user1.jpeg" /> 

       <span> Maya Stones </span> 
    </div> <div class="user-sec">

       <img  class="round" src="../assets/user2.jpeg" /> 

       <span> Jet Philips</span> 
    </div> 
    <div class="user-sec">

       <img  class="round" src="../assets/user3.jpeg" /> 

       <span> Sandra Miller</span> 
    </div> -->
   </div>
    
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  props: {
    users: Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

.side-bar{

       overflow-y: auto;
    width: 30%;
    background: black;
    height: 100vh;
    // width: 250;
    padding: 0rem 0rem 0rem 2rem;
    position: fixed;
    top: 0;
    
}
 .logo{

   width: 13%;
    
 }
 .logo-sec{
       padding-top: 4rem ;
       padding-bottom: 2rem ;

   span{
    
     color: white;
     font-weight: bolder;
     padding: 1rem;
     font-size: 1.3rem;
    

   }
 }

.user-sec{
     margin-top: 2rem;
}

span{

  color:#ffffffc2;
  padding: 1rem;

}

.round{
  
    width: 50px;
    height: 50px;
    border-radius: 9rem;
     object-fit: cover;
  

}

.team{
padding-top: 2rem;

}
</style>
