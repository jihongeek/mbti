<script>
    import DescBox from "./components/DescBox.vue"
    export default {
    data() {
        return {
            typeName: "자유로운 탐험가형",
            typeDescription: `
                특정한 언어나 유행을 벗어나 \n자신만의 길을 가는 유형🤠
                `
            //emoji : Map     
        };
    },
    components: { DescBox }
}
</script>
<template>
    <DescBox :name = typeName :description = typeDescription></DescBox>
</template>