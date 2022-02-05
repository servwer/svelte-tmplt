<script>
let displayedText;
const onSave = () => {
    const wrapper = document.getElementById('wrapper')
    let newWrap;
    if (document.getElementById('test')) {
        document.getElementById('test').remove()
        document.createElement('div')
    } else newWrap = document.createElement('div');
    newWrap.setAttribute('id', 'test')
    const newArray = displayedText.split('\n')
    newArray.map(item => {
        if (item.split('').includes('#')) {
            const count = item.split('').filter(item => item === '#').length
            const newItem = item.split('#').filter(item => item.length > 0)[0];
            const head = document.createElement(`h${count}`)
            head.innerHTML = newItem
            newWrap.appendChild(head);
        } else {
            const text = document.createElement('p')
            text.innerHTML = item;
            newWrap.appendChild(text);
        }
    })
    wrapper.appendChild(newWrap);
}
</script>

<div style="text-align: center; width: 100%; margin: 0 auto;">
    <h1>Editor</h1>
    <div id="wrapper" class='wrapper'>
        <div class='texterea'>
            <textarea bind:value={displayedText}/>
                </div>
                </div>
                <button on:click={onSave}>click</button>
                </div>

<style>
.texterea {
    width: 100%;
}

.texterea textarea::selection {
    -webkit-text-fill-color: firebrick;
}

.texterea textarea {
    width: 500px;
    border: 0;
    outline: 0;
    font-size: 12px;
    height: 600px;
    padding: 5px;
}

#test {
    background-color: #fff;
    width: 600px;
    border: 1px solid black;
}

.wrapper {
    display: flex;
    justify-content: space-between;
}
</style>
