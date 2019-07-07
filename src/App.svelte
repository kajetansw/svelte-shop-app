<script>
    import Product from './Product.svelte';

    let title = '';
    let price = 0;
    let description = '';

    function setTitle(event) {
        title = event.target.value;
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
</section>

<Product />
