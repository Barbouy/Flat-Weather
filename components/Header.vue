<template>
    <div class="container">
        <div class="title"><h1>Flat <span>Weather</span>...</h1></div>
        <div class="quote"><h3><span>Comment</span> vas-tu t'habiller <span>aujourd'hui ?</span></h3></div>
    </div>
</template>
    
<script>
export default {
    
}
</script>

<style scoped>
.container {
    width: 100%;
    height: 8rem;
    flex-direction: column;
    justify-content: center;
}

.title {
    width: 100%;
}

.quote {
    width: 100%;
    padding-left: 2rem;
}

h1, h2 {
    font-family: 'Secular One', sans-serif;
    line-height: 3rem;
}

h1 {
    font-size: 3rem;
    letter-spacing: 3px;
}

h1 span, h3 span {
    color:#ea8685;
}
</style>