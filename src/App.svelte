<script>
    import Product from './Product.svelte';
    import Button from './Button.svelte';

    let title = 'Sample';
    let price = 0;
    let description = 'Description';

    let products = [];

    function setTitle(event) {
        title = event.target.value;
    }

    function createProduct() {
        const newProduct = { title, price, description };
        products = [newProduct, ...products];
    }
</script>

<style>
    section {
        padding: 1rem;
        width: 30rem;
    }

    label, input, textarea {
        width: 100%;
    }
</style>

<section>
    <div>
        <label for="title">Title</label>
        <input id="title" type="text" value={title} on:input={setTitle}>
    </div>
    <div>
        <label for="price">Price</label>
        <input id="price" type="number" value={price} bind:value={price}>
    </div>
    <div>
        <label for="description">Description</label>
        <textarea 
            id="description" 
            rows="3" 
            value={description} 
            bind:value={description}
        />
    </div>

    <Button on:click={createProduct}>Create Product</Button>
</section>

{#if products.length === 0}
    <p>No products were added yet!</p>

    {:else}
    {#each products as product}
        <Product 
            productTitle={product.title} 
            productPrice={product.price} 
            productDescription={product.description} 
        />
    {/each}
{/if}


