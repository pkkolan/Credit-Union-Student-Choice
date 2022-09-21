<template>
<LoansComponent :loansArray="loansArray" />
</template>

<script>
import LoansComponent from './components/LoansComponent.vue';

export default {
    name: 'App',
    components: {
        LoansComponent
    },
    data() {
        return {
            loansArray: [{
                    "name": "Ultimate Credit Union",
                    "Borrower": "Paul Smith",
                    "Amount": "1500"
                },
                {
                    "name": "West Credit Union",
                    "Borrower": "Diane Winters",
                    "Amount": "2000"
                },
                {
                    "name": "Credit Union of the Mountains",
                    "Borrower": "Mark Stone",
                    "Amount": "750"
                },
                {
                    "name": "West Credit Union",
                    "Borrower": "Cindy Block",
                    "Amount": "3500"
                },
                {
                    "name": "Ultimate Credit Union",
                    "Borrower": "Margaret Hill",
                    "Amount": "1000"
                }
            ]
        }
    }

}
</script>

<style>
#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: left;
}
</style>
