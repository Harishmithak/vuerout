<!-- 

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

                <button @click="toggleShow" class="b1">{{ show ? 'Show Less' : 'Show More' }}</button>

                <div v-show="show" class="new">Processor: AMD Ryzen 5 5500U (up to 4.0 GHz max boost clock(2i), 8 MB L3 cache, 6 cores, 12 threads)| Memory: 8 GB DDR4-3200 SDRAM (1 x 8 GB), Upto 16 GB DDR4-3200 MHz RAM (2 x 8 GB) | Storage: 512 GB PCIe NVMe M.2 SSD
                </div>

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
                <br>
                <button @click="toggleShow1" class="b1">{{ show1 ? 'Show Less' : 'Show More' }}</button>

<div v-show="show1" class="new">【High Resolution Display】- Comes with a 1.3" TFT Color Full 
  Touch Screen and a 240*240 Pixel High Resolution this watch is covered to flaunt the sleek
   and stylish look always with 260 NITS Peak Brightness
</div>

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
                <br>
                <button @click="toggleShow2" class="b1">{{ show2 ? 'Show Less' : 'Show More' }}</button>

<div v-show="show2" class="new">Striking 10.9-inch Liquid Retina display with True Tone
A14 Bionic chip with 6-core CPU and 4-core GPU
12MP Wide back camera
Landscape 12MP Ultra Wide front camera with Center Stage
</div>

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
      show: false,
      show1: false,
      show2: false,
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

    },
    toggleShow() {
      this.show = !this.show;
    },
    toggleShow1() {
      this.show1 = !this.show1;
    },
    toggleShow2() {
      this.show2= !this.show2;
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

.fas {
  color: red;
}
.new{
  color: white;
}
.b1{
  background-color: rgb(61, 17, 66);
  border-radius: 7px;
  color:white;
}
</style>   



  -->


  <template>
    <div class="container">
      <div class="home">
        <h1 class="display">Welcome to My Website</h1>
        <p class="lead text-warning">"We look forward to serving you and providing an exceptional online experience!"</p>
        <hr class="my-4">
  
        <div class="container">
          <div class="row">
            <div class="col-md-4" v-for="product in products" :key="product.id">
              <div class="card">
                <img :src="product.image" class="card-img-top" :alt="product.name">
                <div class="card-body">
                  <h5 class="card-title">{{ product.name }}</h5>
                  <i class="fas fa-heart" v-if="product.isFavorite" @click="toggleFavorite(product)"></i>
                  <i class="far fa-heart" v-else @click="toggleFavorite(product)"></i>
                  <h4>Required Quantity: {{ product.quantity }}</h4>
  
                  <br />
                  <button @click="increaseQuantity(product)">+</button> <b>Quantity</b>
                  <button @click="decreaseQuantity(product)">-</button>
                  <br>
                  <button @click="toggleShow(product)" class="b1">{{ product.show ? 'Show Less' : 'Show More' }}</button>
  
                  <div v-show="product.show" class="new">{{ product.description }}</div>
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
  import laptopImage from '../assets/download.jpg';
import watchImage from '../assets/watch.jpg';
 import ipadImage from '../assets/ipad.jpg';

  
  export default {
    data() {
      return {
        products: [
          {
            id: 1,
            name: 'LAPTOP',
            image: laptopImage,
            isFavorite: false,
            quantity: 0,
            show: false,
            description: 'Processor: AMD Ryzen 5 5500U (up to 4.0 GHz max boost clock(2i), 8 MB L3 cache, 6 cores, 12 threads) | Memory: 8 GB DDR4-3200 SDRAM (1 x 8 GB), Upto 16 GB DDR4-3200 MHz RAM (2 x 8 GB) | Storage: 512 GB PCIe NVMe M.2 SSD',
          },
          {
            id: 2,
            name: 'I WATCH',
            image: watchImage,
            isFavorite: false,
            quantity: 0,
            show: false,
            description: '【High Resolution Display】- Comes with a 1.3" TFT Color Full Touch Screen and a 240*240 Pixel High Resolution this watch is covered to flaunt the sleek and stylish look always with 260 NITS Peak Brightness',
          },
          {
            id: 3,
            name: 'I PAD',
            image:ipadImage,
            isFavorite: false,
            quantity: 0,
            show: false,
            description: 'Striking 10.9-inch Liquid Retina display with True Tone. A14 Bionic chip with 6-core CPU and 4-core GPU. 12MP Wide back camera. Landscape 12MP Ultra Wide front camera with Center Stage',
          },
        ],
      };
    },
    methods: {
      decreaseQuantity(product) {
        if (product.quantity > 0) {
          product.quantity--;
        }
      },
      increaseQuantity(product) {
        product.quantity++;
      },
      toggleFavorite(product) {
        product.isFavorite = !product.isFavorite;
      },
      toggleShow(product) {
        product.show = !product.show;
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
    },
  };
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
  
  .fas {
    color: red;
  }
  
  .new {
    color: white;
  }
  
  .b1 {
    background-color: rgb(61, 17, 66);
    border-radius: 7px;
    color: white;
  }
  </style>
  