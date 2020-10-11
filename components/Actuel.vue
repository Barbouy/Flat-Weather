<template>
    <div class="actuel">
        <div class="temp"><h1>{{ this.temp }}</h1>°C</div>
        <div class="info"></div>
    </div>
</template>

<script>
export default {
    props: ['meteoToday'],
    data() {
        return {
            temp : this.meteoToday.main.temp
        }
    }
}
</script>

<style scoped>
.actuel {
    height: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
}

.temp {
    width: 16rem;
    height: 7rem;
    background-color: rgba(225, 225, 225, 0.7);
    box-shadow: 5px 5px rgba(0, 0, 0, 0.3);
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 3rem;
    color: rgba(30, 30, 30, 0.95);
}

</style>