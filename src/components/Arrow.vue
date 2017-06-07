<template>
    <button class="{isLeft: arrow-left, isRight: arrow-right}" v-show="isShow" @click="clickEvent">{{ sign }}</button>
</template>

<script>
    export default {
        name: arrow,
        props: {
            sign: {
                type: String,
                default: '<'
            },
            isLeft: {
                type: Boolean
            },
            isRight: {
                type: Boolean
            },
            isShow: {
                type: Boolean
            }
        },
        methods: {
            clickEvent () {
                alert(this.sign)
            }
        }
    }
</script>

<style>
    button {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        width: 20px;
        height: 20px;
        background: rgba(0, 0, 0, 0.8);
        border-radius: 50%;
        color: white;
    }
    .arrow-left {
        left: 0px
    }
    .arrow-right {
        left: 0px
    }
</style>