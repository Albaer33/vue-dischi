<template>
    <div class="select-wrapper">
        Mostra per genere:
        <select @click="$emit('optionClicked', selectOption)" v-model="selectOption" name="genere" id="genere">
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
    name: 'Select',
    data: function() {
        return {
            selectOption: ''
        };
    }
}
</script>

<style scoped lang="scss">
.select-wrapper {
    text-align: center;
}
</style>