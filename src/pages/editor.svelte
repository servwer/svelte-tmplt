<script>
let displayedText;
let selectedText = ''
const onSave = () => {
    // document.getElementById('testing') && document.getElementById('testing').remove()
    const wrapper = document.getElementById('wrapper')
    const test = document.getElementById('testing')
    if (test.getElementsByTagName('div').length)
        test.getElementsByTagName('div')[0].remove();
    let newWrap = document.createElement('div');
    // newWrap.classList.add('test')
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
            text.style.marginTop = 0
            text.style.marginBottom = 0
            text.innerHTML = item;
            newWrap.appendChild(text);
        }
    })
    test.appendChild(newWrap)
}

document.addEventListener('keydown', function(event) {
    if (event.code == 'KeyS' && event.ctrlKey) {
        event.preventDefault();
        onSave();
    }
});

const getSelectionText = () => {
    var text = "";
    var activeEl = document.activeElement;
    var activeElTagName = activeEl ? activeEl.tagName.toLowerCase() : null;
    if (
        (activeElTagName == "textarea") || (activeElTagName == "input" &&
            /^(?:text|search|password|tel|url)$/i.test(activeEl.type)) &&
        (typeof activeEl.selectionStart == "number")
    ) {
        text = activeEl.value.slice(activeEl.selectionStart, activeEl.selectionEnd);
    } else if (window.getSelection) {
        text = window.getSelection().toString();
    }
    selectedText = text;
    return text;
}

const onAdd = (type) => {
    console.log(displayedText)
    console.log(selectedText)
    console.log(displayedText.indexOf(selectedText) !== -1)
    if (type === 'h1')
        displayedText = displayedText.replace(`${selectedText}`, `#${selectedText}`)
    if (type === 'h2')
        displayedText = displayedText.replace(`${selectedText}`, `##${selectedText}`)
    if (type === 'h3')
        displayedText = displayedText.replace(`${selectedText}`, `###${selectedText}`)
    if (type === 'code')
        displayedText = displayedText.replace(`${selectedText}`, `<code>${selectedText}</code>`)
    // onSave()
}
</script>

<div style="text-align: center; width: 100%; margin: 0 auto;">
    <h1>Editor</h1>
    <div id="wrapper" class='wrapper'>
        <div class='texterea'>
            <ul class="menu">
                <li on:click={() => onAdd('code')}>code</li>
                <li on:click={() => onAdd('h1')}>h1</li>
                <li on:click={() => onAdd('h2')}>h2</li>
                <li on:click={() => onAdd('h3')}>h3</li>
            </ul>
            <textarea on:select={getSelectionText} bind:value={displayedText}/>
                </div>
                <div id="testing"></div>
                </div>
                <!-- <button on:click={onSave}>click</button> -->
                </div>

<style>
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

.paragraph {
    margin-top: 0;
    margin-bottom: 0;
}

#testing {
    background-color: #fff;
    width: 600px;
    border: 1px solid black;
    text-align: left;
}

#testing>p {
    margin: 0;
}

code {
    background: #afafaf61;
    padding: 5px 10px;
}

.menu {
    display: flex;
    justify-content: space-around;
}

.menu li:hover {
    background-color: rgba(214, 214, 214, 0.733);
}

.menu li {
    cursor: pointer;
    padding: 5px 10px;
}

.wrapper {
    display: flex;
    justify-content: space-between;
}
</style>
