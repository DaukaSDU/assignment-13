<template>
<div class="accordion">
    <h2 :class="titlestyle" @click="logic">
        {{ accordion.name || "Some Accordion" }}
    </h2>
    <p :class="descstyle">
        {{ accordion.section || "Some Description" }}
    </p>
</div>
</template>

<script>
export default {
    props: {
        accordion: Object
    },
    methods: {
        logic() {
            if (this.titlestyle === 'accordion__title') {
                this.titlestyle = 'accordion__title active'
                this.descstyle = 'accordion__desc active'
            } else {
                this.titlestyle = 'accordion__title'
                this.descstyle = 'accordion__desc'
            }
        }
    },
    data() {
        return {
            titlestyle: 'accordion__title',
            descstyle: 'accordion__desc',
        }
    }
}
</script>

<style>
.accordion {
    background-color: aqua;
    border: 2px aqua solid;
}

.accordion__title {
    display: flex;
    justify-content: space-between;
    background-color: blue;
    color: #fff;
    padding: 5px 10px;
    cursor: pointer;
}

.accordion__title.active {
    color: orange;
}

.accordion__desc {
    height: 0px;
    font-size: 20px;
    overflow: hidden;
    overflow-y: auto;
    position: relative;
    transition: .5s;
}

.accordion__desc.active {
    height: 150px;
    padding: 5px;
}

.accordion__title::after {
    content: '+';
}

.accordion__title.active::after {
    content: '-';
}
</style>