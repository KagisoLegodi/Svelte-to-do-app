<script>
    //import { Link } from 'svelte-routing';
    import ProductList from './ProductList.svelte';
  
    export let products = [];
  </script>
  
  <div>
    <h1>Welcome to the Svelte E-store!</h1>
    <ProductList {products} />
  </div>
  