<template>
<span class="timeline">
    <span class="timeline__primary">
        <span class="timeline__title">{{ event.title || 'Some Event' }}</span>
        <span class="timeline__desc">{{ event.desc || 'Some Description' }}</span>
    </span>
    <span class="timeline__date">{{ event.date.toLocaleString() || 'Some Date' }}</span>
</span>
</template>

<script>
export default {
    props: {
        event: Object
    }
}
</script>

<style>
.timeline {
    background-color: antiquewhite;
    border-radius: 10px;
    display: flex;
    justify-content: space-between;
    padding: 5px 20px;
    margin: 5px;
    font-size: 20px;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.timeline__primary {
    display: flex;
    flex-direction: column;
}

.timeline__title {
    font-weight: 600;
}

.timeline__date {
    font-size: 18px;
}
</style>