<template>
  <main>
    <div class="admin_window">
        <h1>Tous les poneys</h1>
        <!-- Boutons -->
        <div class="admin_function">
          <a class="button_amazon" href="">Ajouter un poney</a>
          <a class="button_amazon" href="">Ajouter une catégorie</a>
          <a class="button_amazon" href="">Ajouter un propriétaire</a>
        </div>
        <!-- Boutons -->
        <div class="product_grid">
          <div class="product_solo" v-for="(product, index) in products" :key="product._id">
            <!-- <a><img src="/palomino.jpg"/></a> -->
            <a><img :src="product.photo"/></a>
            <a>{{product.title}}, 11</a>
            <div class="product_rating">
              <div class="stars star-4-5"></div>
              <a>10</a>
            </div>
            <div class="product_price">{{product.price}}€</div>
            <div class="product_buttons">
              <a class="button_amazon" href="">Modifier</a>
              <a class="button_amazon" href="">Supprimer</a>
            </div>
          </div>
        </div>
    </div>
  </main>
</template>

<script>
  export default {
    async asyncData({ $axios }) {
      try {
        let response = await $axios.$get("http://localhost:5000/api/products");
        console.log(response);

        return {
          products: response.products
        }
      } catch (err) {
        
      }
    }
  }
</script>

<style lang="scss" scoped>
.admin_window {
  padding: 40px 0 0 40px;
  margin-left: 40px;
  font-family: "Open Sans", Arial, Helvetica, sans-serif;
}
.admin_function {
  display: flex;
  padding: 20px 0;
  a {
    margin-right: 20px;
  }
}

.button_amazon {
    cursor: pointer;
    text-align: center;
    color: #111;
    box-sizing: border-box;
    display: block;
    position: relative;
    padding: .5rem 1rem;
    font-size: 1rem;
    border-radius: 4px;
    background: linear-gradient(to bottom,#f7dfa5,#f0c14b);
    box-shadow: 0 1px 0 rgba(255,255,255,.4) inset;
    border-color: #997a33;
    border-width: 1px;
    border-style: solid;
    text-decoration: none;
    font-weight: 400;
    &:hover {
      background-image: linear-gradient(#f5d78e,#eeb933);
    }
}

.product_grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 1.5rem;
}
@media screen and (min-width: 536px) {
  .product_grid {
    grid-template-columns: repeat(auto-fill,minmax(240px,1fr));
  }
}
.product_solo {
    display: flex;
    flex-direction: column;
    width: 100%;
    position: relative;
    border-bottom: 2px solid #dedede;
    padding-bottom: 1rem;
    img {
      width: 100%;
    }
}
.product_rating {
  display: flex;
  align-items: center;
  margin-top: .25rem;
  a {
    display: inline-block;
    margin-left: .25rem;
  }
}
.stars {
    background-image: url('~@/static/amazon.png');
    background-position: -5px -368px;
    background-repeat: no-repeat no-repeat;
    background-size: 400px 900px;
    display: inline-block;
    font-style: italic;
    height: 18px;
    position: relative;
    vertical-align: bottom;
    width: 80px;
    flex-shrink: 0;
}
.star-4-5 {
  background-position: -175px -368px;
}
.product_price {
  font-weight: bold;
  margin-top: .5rem;
}
.product_buttons {
  display: flex;
  justify-content: space-between;
  margin-top: .5rem;
}
</style>