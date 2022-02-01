<script>
</script>

<div class='wrapper'>
    <div class='info'>
        <h1>Lorem ipsum <span class="text">dolor</span> sit amet consectetur <span class="text">adipisicing</span> elit. Quibusdam sunt iusto ducimus <span class="text">possimus</span>. Illo, magni.</h1>
    </div>
</div>

<style>
.wrapper {
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 20px 100px;
}

.info {
    margin: auto 0;
}

.info h1 {
    font-size: 115px;
    line-height: 120px;
    font-family: 'Poller One', cursive;
    background: #A8FF78;
    background: -webkit-linear-gradient(to bottom right, #099300 0%, #e7eb00 100%);
    background: -moz-linear-gradient(to bottom right, #099300 0%, #e7eb00 100%);
    background: linear-gradient(to bottom right, #099300 0%, #e7eb00 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    /* text-shadow: -5px 5px 0px #099300, -10px 10px 0px #01cccc, -15px 15px 0px #e7eb00; */
    text-shadow: 5px 4px 8px rgba(144, 206, 107, 0.9);
}

.info h1 .text {
    /* background: linear-gradient(to bottom right, #fff 0%, #e7eb00 100%); */
    -webkit-text-fill-color: #fff;
    text-shadow: 5px 4px 8px rgba(144, 206, 107, 0.9);
    /* text-shadow: -5px 5px 0px #099300, -10px 10px 0px #01cccc, -15px 15px 0px #e7eb00; */
}

.info h1 .text::selection {
    -webkit-text-fill-color: transparent;
}
</style>
