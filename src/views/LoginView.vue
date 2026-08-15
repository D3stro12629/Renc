<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')

const login = () => {
    console.log('Email:', email.value)
    console.log('Password:', password.value)
}
</script>

<template>

    <div class="container">

        <div class="row justify-content-center">

            <div class="col-md-5">

                <div class="card shadow mt-5">

                    <div class="card-body p-4">

                        <h2 class="text-center mb-4">
                            Login
                        </h2>

                        <form @submit.prevent="login">

                            <div class="mb-3">

                                <label class="form-label">
                                    Email
                                </label>

                                <input v-model="email" type="email" class="form-control" placeholder="Enter email"
                                    required>

                            </div>

                            <div class="mb-3">

                                <label class="form-label">
                                    Password
                                </label>

                                <input v-model="password" type="password" class="form-control"
                                    placeholder="Enter password" required>

                            </div>

                            <button type="submit" class="btn btn-primary w-100">
                                Login
                            </button>

                        </form>

                        <div class="text-center mt-3">

                            <RouterLink to="/">
                                Back to Home
                            </RouterLink>

                        </div>

                    </div>

                </div>

            </div>

        </div>

    </div>

</template>