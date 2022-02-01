<script>
import Loader from './loader.svelte';
import {
    Router
} from '@sveltech/routify'
import {
    routes
} from '@sveltech/routify/tmp/routes'
let loader = true;

setTimeout(() => {
    loader = false
}, 1500);
</script>

{#if loader}
<Loader />
{/if}
<Router {routes} />

<style>

</style>
