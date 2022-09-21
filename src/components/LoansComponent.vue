<template>
<div v-for="(value, name, index) in unionLoansObject" :key="index">
<h1>{{name}}</h1>
<ul>
    <li v-for="item in value" :key="item">{{item.Borrower}} - {{item.Amount}}</li>
</ul>
</div>
</template>

<script>
export default {
    unionLoansObject: {"A":"B"},
    name: "LoansComponent",
    props: {
        loansArray: Array
    },
    watch: {
        loansArray: function (val){
            this.transformToUnion(val)
        }
    },
    methods:{
        transformToUnion(data) {
            this.unionLoansObject = {}
            data.map(x => {
                if (!Object.keys(this.unionLoansObject).includes(x["name"])) {
                    this.unionLoansObject[x["name"]] = [x]
                } else {
                    this.unionLoansObject[x["name"]].push(x)
                }
            })
        }
    },
    data(){
        return {
            unionLoansObject: ()=>{
                return  this.unionLoansObject
            }
        }
    },
    beforeMount(){
        this.transformToUnion(this.loansArray)
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
</style>
