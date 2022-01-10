<template>
    <div class="select-wrapper">
        Mostra per genere:
        <select v-model="selectOption" name="genere" id="genere">
            <option @click="$emit('optionClicked', selectOption)" value="">All</option>
            <option @click="$emit('optionClicked', selectOption)" value="Rock">Rock</option>
            <option @click="$emit('optionClicked', selectOption)" value="Pop">Pop</option>
            <option @click="$emit('optionClicked', selectOption)" value="Jazz">Jazz</option>
            <option @click="$emit('optionClicked', selectOption)" value="Metal">Metal</option>
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