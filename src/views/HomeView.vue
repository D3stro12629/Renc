<template>
    <div>

        <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
            <div class="container">

                <RouterLink class="navbar-brand" to="/">
                    RenC
                </RouterLink>

                <div class="navbar-nav ms-auto">

                    <RouterLink class="nav-link" to="/">
                        Home
                    </RouterLink>

                    <RouterLink class="nav-link" to="/login">
                        Login
                    </RouterLink>

                </div>

            </div>
        </nav>


        <main class="container py-5">

            <div class="text-center">

                <h1 class="display-4 fw-bold">
                    Welcome to RenC
                </h1>

                <p class="lead">
                    Your website is built with Vue.js and Bootstrap.
                </p>

                <RouterLink to="/login" class="btn btn-primary">
                    Login
                </RouterLink>

            </div>

        </main>

    </div>
</template>