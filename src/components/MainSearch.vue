<script >
export default {
    data() {
        return {
            
            }
        },
        props : {
        typeList : {
            type : Array ,
            required : true 
        }
    }
}
</script>

<template>
    <select class="form-select w-25 mt-3 m-auto" aria-label="Default select example" >
        <option selected>Choose The Archetypes:</option>
        <option v-for="(type , index) in typeList":key="index" value="index">{{type.archetype_name}}</option>
    </select>
</template>

<style lang="scss" scoped>


</style>
