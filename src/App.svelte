<script>
    import Product from './Product.svelte';

	export let name;
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
        <input id="title" type="text">
    </div>
    <div>
        <label for="price">Price</label>
        <input id="price" type="number">
    </div>
    <div>
        <label for="description">Description</label>
        <textarea id="description" rows="3" />
    </div>
</section>

<Product />
