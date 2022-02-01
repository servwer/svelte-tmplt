<script>
import TabsTransition from "@sveltech/routify/runtime/decorators/TabsTransition.svelte";

import Sidebar from './../components/Sidebar/Sidebar.svelte';
</script>

<Sidebar />
<main class="inset">    
    <slot decorator={TabsTransition} />    
</main>

<style>
:global(body) {
    padding: 0;
}

* :global(.inset) {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}

main.inset {
    bottom: 64px;
    overflow: hidden;
}

</style>
