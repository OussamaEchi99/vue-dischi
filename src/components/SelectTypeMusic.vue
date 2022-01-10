<template>
    <div>
        <select @change="$emit('searchDone', selectValue)" v-model="selectValue" name="" id="">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "SelectTypeMusic",
    data: function () {
        return {
            selectValue: '',
        }
    },
}
</script>

<style lang="scss" scoped>

</style>