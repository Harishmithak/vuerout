 <!-- <template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script> -->

<template>
  <div class="container ">
    <div class="home ">
      <h1 class="display">Welcome to My Website</h1>
      <p class="lead text-warning">"We look forward to serving you and providing an exceptional online experience!" </p>
      <hr class="my-4">

      <div class="container ">
        <div class="row">
          <div class="col-md-4">
            <div class="card">
              <img src="../assets/download.jpg" class="card-img-top" alt="Card Image">
              <div class="card-body">
                <h5 class="card-title">LAPTOP</h5>
                <i class="fas fa-heart" v-if="isFavorite" @click="toggleFavorite"></i>
                <i class="far fa-heart" v-else @click="toggleFavorite"></i>

                <h4> Required Quantity : {{ quantity }} </h4>

                <br />
                <button v-on:click="quantity++"> + </button> <b>Quantity </b>
                <button v-on:click="decrease"> - </button><br>
             

              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="card">
              <img src="../assets/watch.jpg" class="card-img-top" alt="Card Image">
              <div class="card-body">
                <h5 class="card-title">I WATCH</h5>

                <i class="fas fa-heart" v-if="isFavorite1" @click="toggleFavorite1"></i>
                <i class="far fa-heart" v-else @click="toggleFavorite1"></i>
                <h4> Required Quantity : {{ quantity1 }} </h4>

                <button v-on:click="quantity1++"> + </button> <b>Quantity </b>
                <button v-on:click="decrease1"> - </button>

              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="card">
              <img src="../assets/ipad.jpg" class="card-img-top" alt="Card Image">
              <div class="card-body">
                <h5 class="card-title">I PAD</h5>
                <i class="fas fa-heart" v-if="isFavorite2" @click="toggleFavorite2"></i>
                <i class="far fa-heart" v-else @click="toggleFavorite2"></i>
                <h4> Required Quantity : {{ quantity2 }} </h4>

                <br />
                <button v-on:click="quantity2++"> + </button> <b>Quantity </b>
                <button v-on:click="decrease2"> - </button>

             </div>
            </div>
          </div>
        </div>
      </div> 



      <button class="btn btn-dark" @click="handleClick" type="button">ABOUT US</button>




    </div>
  </div>
</template>

<script>
import { useRouter } from 'vue-router';


export default {

  data() {
    return ({
      isFavorite: false,
      isFavorite1: false,
      isFavorite2: false,
      quantity: 0,
      quantity1: 0,
      quantity2: 0,

      status: true,
      showComp: true


    })
  },
  methods: {
    decrease() {
      if (this.quantity <= 0)
        this.quantity = 0;
      else
        this.quantity--;
    },
    decrease1() {
      if (this.quantity1 <= 0)
        this.quantity1 = 0;
      else
        this.quantity1--;
    },
    decrease2() {
      if (this.quantity2 <= 0)
        this.quantity2 = 0;
      else
        this.quantity2--;
    },
    toggleFavorite() {
      this.isFavorite = !this.isFavorite;

    },
    toggleFavorite1() {
      this.isFavorite1 = !this.isFavorite1;

    },
    toggleFavorite2() {
      this.isFavorite2 = !this.isFavorite2;

    }

  },



  setup() {
    const router = useRouter();

    const handleClick = () => {
      router.push('/about');
    };


    return {
      $router: router,
      handleClick,

    };
  }
}

</script>

<style>
.logo {
  height: 30px;
  width: 30px;
}

.card {
  background-color: dimgrey;
}

.card-title {
  color: wheat;
  font-family: cursive;
}
.fas{
  color: red;
}
</style>   


