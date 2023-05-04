<template>
    <div class="container">
      <h1>Welcome to our Online Shop</h1>
      <div class="grid">
        <div v-for="product in products" :key="product.id" class="item">
          <img :src="product.image" :alt="product.title" class="image">
          <div class="details">
            <h2>{{ product.title }}</h2>
            <p>{{ product.description }}</p>
            <p>Price: {{ product.price }}$</p>
            <button @click="addToCart(product)">Add to Cart</button>
          </div>
        </div>
      </div>
      <div v-if="cart.length > 0" class="cart">
        <h2>Your Cart:</h2>
        <ul>
          <li v-for="(item, index) in cart" :key="index">
            {{ item.title }} - {{ item.price }}$ <button @click="removeFromCart(index)">Remove</button>
          </li>
        </ul>
        <p>Total: {{ total }}$</p>
        <form>
      <label>Email:</label>
        <input type="email" v-model="email" placeholder="Please enter your E-Mail" required/>
        <button type="submit" @click.prevent="submitForm">Checkout</button>
    </form>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        products: [
  {
    id: 1,
    title: "Archangel CD",
    description: "The debut single of Samurai, a band from Cyberpunk 2077 found by Johnny Silverhand.",
    image: "../src/images/cd-covers/Archangel.jpg",
    price: 9.99
  },
  {
    id: 2,
    title: "The Ballad of Buck Ravers CD",
    description: "A hit single by Samurai, a legendary rock band from Night City.",
    image: "../src/images/cd-covers/TheBalladofBuckRavers.jpg",
    price: 12.99
  },
  {
    id: 3,
    title: "A Like Supreme CD",
    description: "Another great single from Samurai, the band that rocked the streets of Night City.",
    image: "../src/images/cd-covers/ALikeSupreme.jpg",
    price: 11.99
  },
  {
    id: 4,
    title: "Chippin' In CD",
    description: "A classic song from Samurai, the band that fought against Arasaka and the Corporations.",
    image: "../src/images/cd-covers/ChippinIn.jpg",
    price: 14.99
  },
  {
    id: 5,
    title: "Never Fade Away CD",
    description: "The final single of Samurai, a band that became a legend in Night City and beyond.",
    image: "./src/images/cd-covers/NeverFadeAway.jpg",
    price: 10.99
  },
  {
    id: 6,
    title: "Samurai Logo T-SHirt",
    description: "Classic black t-shirt with Samurai logo on the front.",
    image: "./src/images/merch/T-SHirt.png",
    price: 29.99
  },
  {
  id: 7,
  title: 'Samurai Leather Jacket',
  description: 'A high-quality leather jacket inspired by the iconic Samurai band. Featuring a bold red and black design, this jacket is perfect for showing off your love for the legendary rockers.',
  image: './src/images/merch/jacket.jpg',
  price: 249.99
},
{
    id: 8,
    title: 'Samurai Logo Cap',
    description: 'Black cap with embroidered Samurai logo.',
    image: './src/images/merch/cap.jpg',
    price: 24.99
  },
  {
  id: 9,
  title: "Chippin' In T-Shirt",
  description: "Show off your love for Samurai with this stylish Chippin' In t-shirt! Featuring the iconic Samurai logo and Johnny Silverhand's signature guitar, this shirt is perfect for any fan.",
  image: "./src/images/merch/CI-T-SHirt.jpg",
  price: 25.99
}
],
        cart: [],
        total: 0
      }
    },
    methods: {
      addToCart(product) {
        this.cart.push(product)
        this.total += product.price
      },
      removeFromCart(index) {
        this.total -= this.cart[index].price
        this.cart.splice(index, 1)
      },
      submitForm() {
      // Check if the email field is not empty
      if (!this.email) {
        alert('Please enter your email address.')
        return
      }

      // Check if the email data is correct
      if (!this.validateEmail(this.email)) {
        alert('Please enter a valid email address.')
        return
      }

      // If both checks pass, submit the form
      alert('Thank you for your purchase! Please check out your E-mail')
    },
    validateEmail(email) {
      // Regex pattern to validate email format
      const pattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      return pattern.test(email)
    }
    }
  }
  </script>
  
  <style scoped>
  input {
    color:#fff;
    margin-right: 1rem;
    margin-left: 1rem;
    background-color: rgba(0, 0, 0, 0);
    border-radius: 3px;
    border: 1px solid rgba(255, 255, 255, 0.562);
  }
  h1 {
    color: rgba(0, 238, 255, 0.945);
    font-weight: bold;
    font-size: 3rem;
  }
  h2 {
    color: rgba(244, 228, 10, 0.945);
  }
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
  }
  
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
  }
  
  .item {
    color:#fff;
    display: flex;
    flex-direction: column;
    background-color: #14000ae5;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  }
  
  .image {
    opacity: 0.95;
    max-width: 100%;
    height: auto;
    margin-bottom: 20px;
  }
  
  .details {
    flex: 1;
  }
  
  .cart {
    padding: 40px;
    color: white;
    background-color: #14000ae5;
    margin-top: 50px;
    border-top: 2px solid #000;
    padding-top:20px;
}

.cart ul {
list-style: none;
margin: 0;
padding: 0;
}

.cart li {
    border-radius: 3px;
    padding: 1rem;
border: 1px solid rgba(255, 255, 255, 0.548);
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: 10px;
}

.cart li button {
background-color: #700000;
color: #fff;
border: none;
padding: 5px 10px;
border-radius: 5px;
cursor: pointer;
transition: all 0.2s ease-in-out;
}

.cart li button:hover {
background-color: #fff;
color: #ff0000;
border: 2px solid #ff0000;
}

button {
border: 1px solid rgba(255, 255, 255, 0.74);
background-color: #000;
color: #fff;
padding: 5px 10px;
border-radius: 5px;
cursor: pointer;
transition: all 0.2s ease-in-out;
}

button:hover {
background-color: #fff;
color: #000;
border: 2px solid #000;
}
</style>