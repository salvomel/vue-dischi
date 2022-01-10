<template>
    <div class="container">
        <div class="select-wrapper">
            <select @change="$emit('selectClicked', selectValue)" v-model="selectValue" class="form-select" aria-label="Default select example">
                <option value="All">Tutti i generi</option>
                <option value="Pop">Pop</option>
                <option value="Rock">Rock</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: "Select",
    data: function () {
        return {
            selectValue: 'All'
        };
    },
}
</script>

<style scoped lang="scss">
.select-wrapper {
    
    padding: 40px 120px;
}
</style>
