<script>
import {
    url,
    isActive
} from '@sveltech/routify'
export let links = [
    ['./index', 'Home'],
    ['./info', 'Info'],
    ['./editor', 'Editor']
]
</script>

<div class="navbar">
    <ul>
        {#each links as [path, name] }
        <li class:selected={$isActive(path)} class="navbar-item"><a href={$url(path)}>{name}</a></li>
        {/each}
    </ul>
</div>

<style>
a {
    text-decoration: none;
    padding: 7px 14px;
    width: 100%;
}

.navbar {
    max-width: 150px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: left;
    height: 100vh;
    border-right: 1px dashed #099300;
    padding: 0 10px;
    position: relative;
}

.navbar-item {
    font-size: 20px;
    padding: 10px 20px;
    position: relative;
    background: -webkit-linear-gradient(to bottom right, #099300 0%, #e7eb00 100%);
    background: -moz-linear-gradient(to bottom right, #099300 0%, #e7eb00 100%);
    background: linear-gradient(to bottom right, #099300 0%, #e7eb00 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 5px 4px 8px rgba(144, 206, 107, 0.9);
}

li.selected::after {
    position: absolute;
    content: '1231212343';
    top: 0;
    left: 0;
}

ul {
    margin: 0;
    padding: 0;
}
</style>
