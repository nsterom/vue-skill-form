<template>
    <div class="container">
        <form v-if="!summited">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->
                        <app-full-name v-model="fullName"></app-full-name>
                        <div class="form-group">
                            <label>Mail</label>
                            <input type="text" class="form-control" v-model="mail">
                        </div>
                        <div class="form-group">
                            <label>Password</label>
                            <input type="password" class="form-control" v-model="password">
                        </div>
                        <div class="form-group">
                            <label>Store Data?</label>
                            <label for="Yes">
                                <input type="radio" id="Yes" value="Yes" v-model="isSave"> Yes
                            </label>
                            <label for="No">
                                <input type="radio" id="No" value="No" v-model="isSave"> No
                            </label>
                        </div>
                        <button class="btn btn-primary" v-on:click.prevent="summited = true">Summit</button>
                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="summited">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName }}</p>
                        <p>Mail: {{ mail }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ isSave }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './FullName.vue'

    export default {
        data: function() {
            return {
                fullName: 'hello world2',
                // firstName: '',
                // lastName: '',
                mail: '',
                password: '',
                isSave: 'Yes',
                summited: false
            }
        },
        components: {
            'app-full-name': FullName
        }
    }
</script>

<style>
</style>
