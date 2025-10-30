<template>
    <button @click="getTheCity">
        {{ text }}
    </button>
</template>

<script>
export default {
    name: "MyButton",
    props: {
        text: String
        
    }
}
</script>