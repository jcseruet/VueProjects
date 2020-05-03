<template>
    <div class="form-group row">
        <label class="col-2" for="Age">Age</label>
        <input class="form-control col-4 leftAlign" id="Age" name="Age" type="text" v-model="age" v-validate="'required|min_value:0'"> 
        <div class="text-danger" v-if="errors.has('Age')">{{errors.first('Age')}}</div>
        <div class="text-warning" v-if="showWarning()">Warning: Age has changed from 36</div>
    </div>
</template>

<script>
export default {
    data(){
        return {    
            age: 36
        }
    },
    methods:{
        showWarning(){
            var hasError = this.errors.has('Age');
            if(this.age == 36 || hasError)
                return false;
            else
                return true;
        }
    }
}
</script>
<style scoped>
.leftAlign{
    text-align: left;
}
</style>