<template>
    <div @click="open" class="threshold">
        <h2>{{randomPrize}}</h2>
        <div class="door" :class="{'open-close' : isOpen}">
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    isOpen: {
        type: Boolean,
        required: true
    },
    randomPrize: {
        type: String,
        required: true
    },
    id: {
        type: Number
    }
})

const emit = defineEmits(['open'])

const open = () => {
    emit('open', props.id)
}
</script>

<style scoped>
.threshold {
    position: relative;
    width: 200px;
    height: 200px;
    background-color: #FFFFFF;
    border: 2px solid #000000;
    cursor: pointer;
    margin-left: 20px;
}

.door {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: #FF0000;
    transform-style: preserve-3d;
    perspective: 550px;
    transform-origin: 0 50%;
    transition: all 1s;
}

.open-close {
    transform: scale(0.05, 1) skew(0deg, 20deg);
}

</style>