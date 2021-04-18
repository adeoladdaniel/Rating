<template>
<div>
 <div class="user-info">
    <div class="user-desc">
         <img src="../assets/user.jpeg"/>
         <h5>Adeola Daniel</h5>
         <p>Front-end Developer</p>
    </div>
 <h1 class="rated">Rating Summary</h1>
        <div class="rate">
            <input type="radio" id="star5" name="rate" value="7" />
    <label for="star5" title="text">5 stars</label>
            <input type="radio" id="star5" name="rate" value="6" />
    <label for="star5" title="text">5 stars</label>
    <input type="radio" id="star5" name="rate" value="5" />
    <label for="star5" title="text">5 stars</label>
    <input type="radio" id="star4" name="rate" value="4" />
    <label for="star4" title="text">4 stars</label>
    <input type="radio" id="star3" name="rate" value="3" />
    <label for="star3" title="text">3 stars</label>
    <input type="radio" id="star2" name="rate" value="2" />
    <label for="star2" title="text">2 stars</label>
    <input type="radio" id="star1" name="rate" value="1" />
    <label for="star1" title="text">1 star</label>
  </div>
 
 </div>
 <Rating/>


 <SideBar v-bind:users="users"/>
</div>
</template>

<script>
// @ is an alias to /src
import SideBar from '@/components/SideBar.vue'
import users from './user.json'




export default {
  name: 'Home',
  components: {
    SideBar,
    
  },

  data(){
     return{
        users
     }
  },
  mounted(){
     console.log(typeof(users));
  }
}
</script>

<style lang="scss">
.user-info{
       margin-left: 30%;
    padding: 2rem 2rem;
}

.user-desc{
   margin-left: auto;
   margin-right: auto;
   img{
           width: 20%;
    border-radius: 7rem;
    height: 10rem;
    object-fit: cover;
   }
   h5{
          padding: 0rem 2rem;
   }
   p{
          padding: 0rem 2rem;
   }

}
.rated{
   color: #0299f6;
}

.rate {
    float: left;
    height: 46px;
    padding: 0 10px;
}
.rate:not(:checked) > input {
    position:absolute;
    top:-9999px;
}
.rate:not(:checked) > label {
    float:right;
    width:1em;
    overflow:hidden;
    white-space:nowrap;
    cursor:pointer;
    font-size:30px;
    color:#ccc;
}
.rate:not(:checked) > label:before {
    content: '★ ';
}
.rate > input:checked ~ label {
    color: #ffc700;    
}
.rate:not(:checked) > label:hover,
.rate:not(:checked) > label:hover ~ label {
    color: #deb217;  
}
.rate > input:checked + label:hover,
.rate > input:checked + label:hover ~ label,
.rate > input:checked ~ label:hover,
.rate > input:checked ~ label:hover ~ label,
.rate > label:hover ~ input:checked ~ label {
    color: #c59b08;
}

</style>