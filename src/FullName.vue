<template>
    <div>
        <div class="form-group">
            <label>First Name</label>
            <input type="text" class="form-control" v-bind:value="firstName" v-on:input="nameChanged(true, $event)"/>
        </div>
        <div class="form-group">
            <label>Last Name</label>
            <input type="text" class="form-control" v-bind:value="lastName" v-on:input="nameChanged(false, $event)"/>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['value'],
        methods: {
            nameChanged: function(isFirst, event) {
                let name = ''
                if (isFirst) {
                    // this.value = name + this.value.split(" ")[1]
                    name = event.target.value + ' ' + this.lastName
                } else {
                    // this.value = this.value.split(" ")[0] + name
                    name = this.firstName + ' ' + event.target.value
                }
                this.value = name
                this.$emit('input', this.value)
            }
        },
        computed: {
            firstName: function() {
                return this.value.split(" ")[0]
            },
            lastName: function() {
                return this.value.split(" ")[1]
            }
        }
    }
</script>