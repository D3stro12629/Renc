<script setup>
import { reactive, ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()

const form = reactive({
    username: '',
    password: '',
    remember: false
})

const errors = reactive({
    username: '',
    password: ''
})

const showPassword = ref(false)
const submitting = ref(false)
const submitError = ref('')


/* ================= VALIDATION ================= */

function validate() {

    errors.username = form.username
        ? ''
        : 'Username is required.'

    errors.password = form.password
        ? ''
        : 'Password is required.'

    return !errors.username && !errors.password
}


/* ================= LOGIN ================= */

async function handleSubmit() {

    submitError.value = ''

    if (!validate()) {
        return
    }

    submitting.value = true

    try {

        /*
          Later you can replace this with:
    
          await authStore.login(form)
    
          or
    
          await api.post('/auth/login', form)
        */

        console.log('Login:', form)

        // Example:
        // router.push('/')

    } catch (error) {

        submitError.value =
            'Login failed. Please check your credentials.'

    } finally {

        submitting.value = false

    }
}


/* ================= REGISTER ================= */

function goToRegister() {

    router.push('/register')

}
</script>


<template>

    <div class="login-page">

        <div class="login-card">

            <!-- LOGO -->

            <div class="login-logo">
                RenC<span>.</span>
            </div>


            <!-- TITLE -->

            <h1>
                Welcome Back
            </h1>

            <p class="login-subtitle">
                Login to your account
            </p>


            <!-- FORM -->

            <form @submit.prevent="handleSubmit" novalidate>

                <!-- USERNAME -->

                <div class="form-group">

                    <label>
                        Username
                    </label>

                    <div class="input-wrapper" :class="{ error: errors.username }">

                        <i class="fa-solid fa-user"></i>

                        <input type="text" placeholder="Enter your username" v-model.trim="form.username">

                    </div>

                    <small v-if="errors.username" class="error-message">
                        {{ errors.username }}
                    </small>

                </div>


                <!-- PASSWORD -->

                <div class="form-group">

                    <label>
                        Password
                    </label>

                    <div class="input-wrapper" :class="{ error: errors.password }">

                        <i class="fa-solid fa-lock"></i>

                        <input :type="showPassword ? 'text' : 'password'" placeholder="Enter your password"
                            v-model="form.password">

                        <button type="button" class="password-button" @click="showPassword = !showPassword">

                            <i :class="showPassword
                                    ? 'fa-solid fa-eye-slash'
                                    : 'fa-solid fa-eye'
                                "></i>

                        </button>

                    </div>

                    <small v-if="errors.password" class="error-message">
                        {{ errors.password }}
                    </small>

                </div>


                <!-- REMEMBER / FORGOT -->

                <div class="login-options">

                    <label class="remember">

                        <input type="checkbox" v-model="form.remember">

                        <span>
                            Remember me
                        </span>

                    </label>


                    <a href="#" @click.prevent>
                        Forgot Password?
                    </a>

                </div>


                <!-- ERROR -->

                <div v-if="submitError" class="submit-error">
                    {{ submitError }}
                </div>


                <!-- LOGIN BUTTON -->

                <button type="submit" class="login-button" :disabled="submitting">

                    <span v-if="submitting" class="spinner"></span>

                    {{
                        submitting
                            ? 'Logging in...'
                            : 'Login'
                    }}

                </button>


                <!-- REGISTER -->

                <p class="register-text">

                    Don't have an account?

                    <a href="#" @click.prevent="goToRegister">
                        Register
                    </a>

                </p>

            </form>

        </div>

    </div>

</template>


<style scoped>
/* ================================================= */
/* PAGE */
/* ================================================= */

.login-page {

    min-height: 100vh;
    width: 100%;

    display: flex;

    align-items: center;
    justify-content: center;

    padding: 30px 20px;

    background:
        linear-gradient(135deg,
            #16222a,
            #3a6073);

}


/* ================================================= */
/* CARD */
/* ================================================= */

.login-card {

    width: 100%;
    max-width: 420px;

    padding: 45px 35px;

    border-radius: 20px;

    background:
        rgba(255, 255, 255, 0.08);

    backdrop-filter: blur(15px);

    -webkit-backdrop-filter: blur(15px);

    border:
        1px solid rgba(255, 255, 255, 0.15);

    box-shadow:
        0 15px 50px rgba(0, 0, 0, 0.35);

    color: white;

}


/* ================================================= */
/* LOGO */
/* ================================================= */

.login-logo {

    text-align: center;

    font-family: "Ubuntu", sans-serif;

    font-size: 38px;

    font-weight: 700;

    margin-bottom: 25px;

}

.login-logo span {

    color: #c97e5f;

}


/* ================================================= */
/* TITLE */
/* ================================================= */

.login-card h1 {

    text-align: center;

    font-size: 30px;

    font-weight: 600;

    margin: 0;

}

.login-subtitle {

    text-align: center;

    color:
        rgba(255, 255, 255, 0.65);

    font-size: 14px;

    margin-top: 8px;

    margin-bottom: 30px;

}


/* ================================================= */
/* FORM */
/* ================================================= */

.form-group {

    margin-bottom: 20px;

}

.form-group label {

    display: block;

    font-size: 14px;

    margin-bottom: 8px;

    color:
        rgba(255, 255, 255, 0.9);

}


/* ================================================= */
/* INPUT */
/* ================================================= */

.input-wrapper {

    display: flex;

    align-items: center;

    width: 100%;

    height: 50px;

    padding: 0 15px;

    border-radius: 10px;

    background:
        rgba(255, 255, 255, 0.08);

    border:
        1px solid rgba(255, 255, 255, 0.15);

    transition: 0.3s;

}

.input-wrapper:focus-within {

    border-color: #c97e5f;

    background:
        rgba(255, 255, 255, 0.12);

    box-shadow:
        0 0 0 3px rgba(201, 126, 95, 0.15);

}

.input-wrapper.error {

    border-color: #ff5c5c;

}

.input-wrapper>i {

    margin-right: 12px;

    color:
        rgba(255, 255, 255, 0.6);

}

.input-wrapper input {

    flex: 1;

    width: 100%;

    border: none;

    outline: none;

    background: transparent;

    color: white;

    font-size: 14px;

}

.input-wrapper input::placeholder {

    color:
        rgba(255, 255, 255, 0.45);

}


/* ================================================= */
/* PASSWORD BUTTON */
/* ================================================= */

.password-button {

    border: none;

    background: transparent;

    color:
        rgba(255, 255, 255, 0.6);

    cursor: pointer;

    padding: 5px;

}

.password-button:hover {

    color: white;

}


/* ================================================= */
/* ERROR */
/* ================================================= */

.error-message {

    display: block;

    margin-top: 6px;

    color: #ff7272;

    font-size: 12px;

}


/* ================================================= */
/* OPTIONS */
/* ================================================= */

.login-options {

    display: flex;

    align-items: center;

    justify-content: space-between;

    margin-bottom: 25px;

    font-size: 13px;

}

.remember {

    display: flex;

    align-items: center;

    gap: 7px;

    cursor: pointer;

    color:
        rgba(255, 255, 255, 0.75);

}

.remember input {

    accent-color: #c97e5f;

}

.login-options a {

    color: #c97e5f;

    text-decoration: none;

}

.login-options a:hover {

    text-decoration: underline;

}


/* ================================================= */
/* ERROR ALERT */
/* ================================================= */

.submit-error {

    padding: 10px 12px;

    margin-bottom: 15px;

    border-radius: 8px;

    background:
        rgba(255, 80, 80, 0.15);

    border:
        1px solid rgba(255, 80, 80, 0.3);

    color: #ff8a8a;

    font-size: 13px;

}


/* ================================================= */
/* LOGIN BUTTON */
/* ================================================= */

.login-button {

    width: 100%;

    height: 50px;

    border: none;

    border-radius: 10px;

    background: #c97e5f;

    color: white;

    font-size: 16px;

    font-weight: 600;

    cursor: pointer;

    transition: 0.3s;

}

.login-button:hover {

    background: #d98d6e;

    transform: translateY(-2px);

}

.login-button:disabled {

    opacity: 0.7;

    cursor: not-allowed;

    transform: none;

}


/* ================================================= */
/* SPINNER */
/* ================================================= */

.spinner {

    display: inline-block;

    width: 16px;

    height: 16px;

    margin-right: 8px;

    border:
        2px solid rgba(255, 255, 255, 0.4);

    border-top-color: white;

    border-radius: 50%;

    animation:
        spin 0.7s linear infinite;

}

@keyframes spin {

    to {
        transform: rotate(360deg);
    }

}


/* ================================================= */
/* REGISTER */
/* ================================================= */

.register-text {

    text-align: center;

    margin-top: 25px;

    margin-bottom: 0;

    color:
        rgba(255, 255, 255, 0.65);

    font-size: 14px;

}

.register-text a {

    color: #c97e5f;

    font-weight: 600;

    text-decoration: none;

    margin-left: 5px;

}

.register-text a:hover {

    text-decoration: underline;

}


/* ================================================= */
/* MOBILE */
/* ================================================= */

@media (max-width: 576px) {

    .login-page {

        padding: 20px 15px;

    }

    .login-card {

        padding: 35px 22px;

        border-radius: 16px;

    }

    .login-logo {

        font-size: 32px;

        margin-bottom: 20px;

    }

    .login-card h1 {

        font-size: 26px;

    }

    .login-subtitle {

        margin-bottom: 25px;

    }

    .login-options {

        font-size: 12px;

    }

}


/* ================================================= */
/* SMALL PHONES */
/* ================================================= */

@media (max-width: 375px) {

    .login-page {

        padding: 15px 10px;

    }

    .login-card {

        padding: 30px 18px;

    }

    .login-options {

        flex-direction: column;

        align-items: flex-start;

        gap: 12px;

    }

    .login-button {

        height: 48px;

    }

}
</style>