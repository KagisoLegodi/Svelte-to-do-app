<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
  
    export let products = [];
  
    const selectProduct = (/** @type {any} */ product) => {
      dispatch('select', product);
    };
  </script>
  
  <style>
    .product-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }
    .product-card {
      border: 1px solid #090808;
      padding: 1rem;
      border-radius: 8px;
      cursor: pointer;
      width: 200px;
      background-color: white;
    }
  </style>
  
  <div class="product-list">
    {#each products as product}
      <!-- svelte-ignore a11y-no-static-element-interactions -->
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div class="product-card" on:click={() => selectProduct(product)}>
        <img src={product.image} alt={product.title} width="100" height="100" />
        <h2>{product.title}</h2>
        <p>${product.price}</p>
        <p>Rating: { product.rating.rate} ({ product.rating.count} reviews)</p>
      <p>${ product.price}</p>
      </div>
    {/each}
  </div>
