<script setup>
import { ref, onMounted } from 'vue'

import AOS from 'aos'
import 'aos/dist/aos.css'

import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper/modules'
import 'swiper/css'

// ================= IMAGES =================

import heroImage from '../assets/images/rolls_royce_boat_tail_2022_4kk.jpg'
import aboutImage from '../assets/images/koe-goblin.avif'
import experienceImage from '../assets/images/Rolls-Royce-Boat-Tail.jpg'
import bentleyImage from '../assets/images/green-bentley.jpg'

import mclarenImage from '../assets/images/750s.avif'
import nissanImage from '../assets/images/2015_nissan_gt_r_sideview.jpg'
import lamboImage from '../assets/images/lamborghini-aventador.jpg'
import porscheImage from '../assets/images/porssss.jpg'

import slide1 from '../assets/images/pexels-photo-3802510.webp'
import slide2 from '../assets/images/lam-4k.jpg'
import slide3 from '../assets/images/chiron-super-sport-300.jpg'
import slide4 from '../assets/images/chiron-pur-sport-dynamisch.jpg'

// ================= AOS =================

onMounted(() => {
    AOS.init({
        duration: 900,
        once: true
    })
})

// ================= LANGUAGE =================

const language = ref('Eng')

const changeLanguage = () => {
    language.value = language.value === 'Eng' ? 'KH' : 'Eng'
}

// ================= VEHICLES =================

const vehicles = [
    {
        name: 'McLaren 720S',
        price: '$420',
        image: mclarenImage
    },
    {
        name: 'Nissan GT-R 35',
        price: '$330',
        image: nissanImage
    },
    {
        name: 'Lamborghini Aventador SVJ',
        price: '$540',
        image: lamboImage
    },
    {
        name: 'Porsche GT3 RS',
        price: '$500',
        image: porscheImage
    }
]

// ================= SLIDES =================

const slides = [
    'https://images.collectingcars.com/006173/IMG-0381.jpg?w=1263&fit=fillmax&crop=edges&auto=format,compress&cs=srgb&q=85',
    slide1,
    slide2,
    slide3,
    slide4
]
</script>

<template>

    <!-- ================================================= -->
    <!-- NAVBAR -->
    <!-- ================================================= -->

    <header>

        <nav class="navbar navbar-expand-lg fixed-top">

            <div class="container">

                <!-- MOBILE BUTTON -->

                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#mainNavbar"
                    aria-controls="mainNavbar" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>


                <!-- NAVBAR -->

                <div id="mainNavbar" class="collapse navbar-collapse">

                    <!-- LEFT -->

                    <ul class="navbar-nav gap-lg-2">

                        <li class="nav-item">
                            <a class="nav-link" href="#booking">
                                Booking
                            </a>
                        </li>

                        <li class="nav-item">
                            <a class="nav-link" href="#vehicles">
                                Vehicles
                            </a>
                        </li>

                        <li class="nav-item">
                            <a class="nav-link" href="#about">
                                About
                            </a>
                        </li>

                        <li class="nav-item">
                            <a class="nav-link" href="#contact">
                                Contact
                            </a>
                        </li>

                    </ul>


                    <!-- LOGO -->

                    <a href="#" class="navbar-brand mx-lg-auto">
                        RenC<span>.</span>
                    </a>


                    <!-- RIGHT -->

                    <div class="navbar-right d-flex align-items-center">

                        <button class="btn-navbar" @click="changeLanguage">
                            {{ language }}
                        </button>

                        <router-link to="/login" class="link-profile">
                            <i class="bi bi-person"></i>
                        </router-link>

                    </div>

                </div>

            </div>

        </nav>

    </header>


    <!-- ================================================= -->
    <!-- MAIN -->
    <!-- ================================================= -->

    <main>


        <!-- ================================================= -->
        <!-- HERO -->
        <!-- ================================================= -->

        <section id="booking" class="hero-section">

            <img :src="heroImage" class="hero-img" alt="Luxury car">

            <div class="hero-overlay"></div>


            <div class="container hero-content">

                <h1 class="hero-title">
                    Luxury car
                    <br>
                    rental
                </h1>

                <button class="btn-banner">
                    Rent now
                </button>

            </div>


            <!-- BOOKING -->

            <div class="booking-wrapper">

                <div class="row align-items-center">

                    <!-- PICKUP ADDRESS -->

                    <div class="col-lg-3 col-md-6 booking-item">

                        <div class="booking-content">

                            <h3>
                                Pick Up Address
                            </h3>

                            <p>
                                From: address, airport...
                            </p>

                        </div>

                    </div>


                    <!-- DATE -->

                    <div class="col-lg-3 col-md-6 booking-item">

                        <div class="booking-content">

                            <h3>
                                Pick Up Date
                            </h3>

                            <p>
                                JUN 11, 2025
                            </p>

                        </div>

                    </div>


                    <!-- TIME -->

                    <div class="col-lg-3 col-md-6 booking-item">

                        <div class="booking-content">

                            <h3>
                                Pick Up Time
                            </h3>

                            <p>
                                12:00 AM
                            </p>

                        </div>

                    </div>


                    <!-- BUTTON -->

                    <div class="col-lg-3 col-md-6">

                        <button class="booking-button">

                            <i class="bi bi-calendar3"></i>

                            <span>
                                Book Now
                            </span>

                        </button>

                    </div>

                </div>

            </div>

        </section>


        <!-- ================================================= -->
        <!-- ABOUT -->
        <!-- ================================================= -->

        <section id="about" class="about-section">

            <div class="container">

                <div class="row g-4 align-items-center">

                    <!-- TEXT -->

                    <div class="col-lg-4">

                        <div class="about-text">

                            <h1>
                                About Us
                            </h1>

                            <p>
                                Lorem ipsum dolor sit amet consectetur
                                adipisicing elit. Aut fugit pariatur
                                officiis quos alias quidem deserunt
                                recusandae quod asperiores.
                            </p>

                        </div>

                    </div>


                    <!-- IMAGE -->

                    <div class="col-lg-4">

                        <div class="about-image-wrapper" data-aos="fade-right">

                            <img :src="aboutImage" class="about-image" alt="Luxury vehicle">

                        </div>

                    </div>


                    <!-- EXPERIENCE -->

                    <div class="col-lg-4">

                        <div class="experience-card" data-aos="fade-left">

                            <div class="experience">

                                <h1>
                                    +10 years
                                </h1>

                                <p>
                                    Experience
                                </p>

                            </div>


                            <div class="experience-image" data-aos="fade-up-left">

                                <img :src="experienceImage" alt="Rolls Royce">

                            </div>

                        </div>

                    </div>

                </div>

            </div>

        </section>


        <!-- ================================================= -->
        <!-- BEST OFFER -->
        <!-- ================================================= -->

        <section class="offer-section">

            <div class="container">

                <div class="row g-0">

                    <div class="col-lg-6">

                        <div class="offer-content">

                            <h1>
                                Best Offer
                            </h1>

                            <h3>
                                Bentley Flying Spur
                            </h3>

                            <p>
                                for $400/
                                <span>day</span>
                            </p>

                            <button>
                                Rent Now
                            </button>

                        </div>

                    </div>


                    <div class="col-lg-6">

                        <div class="offer-image">

                            <img :src="bentleyImage" alt="Bentley Flying Spur">

                        </div>

                    </div>

                </div>

            </div>

        </section>


        <!-- ================================================= -->
        <!-- SLIDER -->
        <!-- ================================================= -->

        <section class="slider-section">

            <div class="container">

                <Swiper :modules="[Autoplay]" :slides-per-view="1" :space-between="0" :loop="true" :autoplay="{
                    delay: 2000,
                    disableOnInteraction: false
                }" class="mySwiper">

                    <SwiperSlide v-for="(slide, index) in slides" :key="index">

                        <img :src="slide" alt="Luxury car">

                    </SwiperSlide>

                </Swiper>

            </div>

        </section>


        <!-- ================================================= -->
        <!-- VEHICLES -->
        <!-- ================================================= -->

        <section id="vehicles" class="vehicles-section">

            <div class="container">

                <h1 class="section-title">
                    Vehicles
                </h1>


                <div class="row g-4">

                    <div v-for="vehicle in vehicles" :key="vehicle.name" class="col-xl-3 col-lg-3 col-md-6 col-12">

                        <div class="vehicle-card">

                            <div class="vehicle-info">

                                <h2>
                                    {{ vehicle.name }}
                                </h2>

                                <p>
                                    {{ vehicle.price }}/
                                    <span>day</span>
                                </p>

                            </div>


                            <div class="vehicle-image">

                                <img :src="vehicle.image" :alt="vehicle.name">

                            </div>

                        </div>

                    </div>

                </div>

            </div>

        </section>

    </main>


    <!-- ================================================= -->
    <!-- FOOTER -->
    <!-- ================================================= -->

    <footer id="contact" class="footer">

        <div class="container">

            <div class="row g-5">

                <!-- COMPANY -->

                <div class="col-lg-4 col-md-6">

                    <h2 class="footer-logo">
                        renc
                    </h2>

                    <p>
                        Via Callicratide 36
                        <br>
                        Roisan, Aosta(AO), 11100
                        <br>
                        0321 0575190
                    </p>


                    <div class="social-icons">

                        <a href="#">
                            <i class="bi bi-youtube"></i>
                        </a>

                        <a href="#">
                            <i class="bi bi-facebook"></i>
                        </a>

                        <a href="#">
                            <i class="bi bi-twitter-x"></i>
                        </a>

                        <a href="#">
                            <i class="bi bi-instagram"></i>
                        </a>

                        <a href="#">
                            <i class="bi bi-linkedin"></i>
                        </a>

                    </div>

                </div>


                <!-- RENTERS -->

                <div class="col-lg-2 col-md-6">

                    <h3>
                        For Renters
                    </h3>

                    <ul>

                        <li>
                            <a href="#about">
                                About Us
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                How it works
                            </a>
                        </li>

                        <li>
                            <a href="#vehicles">
                                Our fleet
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                FAQs
                            </a>
                        </li>

                        <li>
                            <a href="#contact">
                                Contact
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                Locations
                            </a>
                        </li>

                    </ul>

                </div>


                <!-- RESOURCES -->

                <div class="col-lg-2 col-md-6">

                    <h3>
                        Resources
                    </h3>

                    <ul>

                        <li>
                            <a href="#">
                                Media & Blog
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                Partners
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                Privacy policy
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                Cookies policy
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                Legal information
                            </a>
                        </li>

                        <li>
                            <a href="#">
                                Help center
                            </a>
                        </li>

                    </ul>

                </div>


                <!-- CONTACT -->

                <div class="col-lg-4 col-md-6">

                    <h3>
                        Contact Us
                    </h3>

                    <p>
                        <strong>
                            Monday - Sunday
                        </strong>

                        <br>

                        8:00 AM - 5:00 PM
                    </p>

                    <p>
                        <strong>
                            Hotline
                        </strong>

                        <br>

                        (+855) 61-910-623
                    </p>

                    <p>
                        <strong>
                            Email
                        </strong>

                        <br>

                        <a href="mailto:zerwestin23@gmail.com">
                            zerwestin23@gmail.com
                        </a>
                    </p>

                </div>

            </div>


            <div class="footer-bottom">

                © 2025 Renc LLC. All rights reserved

            </div>

        </div>

    </footer>

</template>


<style scoped>
/* ================================================= */
/* NAVBAR */
/* ================================================= */

header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
}

.navbar {
    padding: 20px 0;
}

.navbar-brand {
    color: white;
    font-size: 30px;
    font-weight: 700;
    font-family: "Ubuntu", sans-serif;
}

.navbar-brand:hover {
    color: white;
}

.navbar-brand span {
    color: #c97e5f;
}

.nav-link {
    color: white !important;
    font-size: 18px;
    padding: 8px 10px !important;
}

.nav-link:hover {
    color: #c97e5f !important;
}

.navbar-toggler {
    background: white;
    border: none;
}

.navbar-right {
    gap: 10px;
}

.btn-navbar {
    padding: 5px 15px;
    border: 1px solid #777;
    border-radius: 5px;
    background: transparent;
    color: white;
}

.link-profile {
    color: black;
    text-decoration: none;
}

.link-profile i {
    display: flex;
    align-items: center;
    justify-content: center;

    width: 40px;
    height: 40px;

    border-radius: 50%;
    background: white;

    font-size: 20px;
}


/* ================================================= */
/* HERO */
/* ================================================= */

.hero-section {
    min-height: 97vh;
    position: relative;
    display: flex;
    align-items: center;
    overflow: visible;
}

.hero-img {
    position: absolute;
    inset: 0;

    width: 100%;
    height: 100%;

    object-fit: cover;
}

.hero-overlay {
    position: absolute;
    inset: 0;

    background: rgba(0, 0, 0, 0.25);
}

.hero-content {
    position: relative;
    z-index: 2;
}

.hero-title {
    color: white;

    font-family: "Ubuntu", sans-serif;

    font-size: clamp(42px, 6vw, 70px);

    font-weight: 300;

    line-height: 1.1;

    margin-bottom: 20px;
}

.btn-banner {
    background: #c97e5f;
    border: none;
    border-radius: 10px;

    color: white;

    font-size: 17px;

    padding: 10px 20px;

    transition: 0.4s;
}

.btn-banner:hover {
    background: #c97f5f;
    transform: translateY(-2px);
}


/* ================================================= */
/* BOOKING */
/* ================================================= */

.booking-wrapper {
    position: absolute;

    z-index: 10;

    left: 50%;
    bottom: -23px;

    transform: translateX(-50%);

    width: min(1200px, 90%);

    background: white;

    padding: 30px 40px;

    border-radius: 5px;

    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
}

.booking-item {
    border-right: 1px solid #777;
}

.booking-item h3 {
    font-size: 18px;
    color: #777;
    font-weight: 400;
}

.booking-item p {
    margin-top: 15px;
    font-family: "Poppins", sans-serif;
}

.booking-button {
    width: 100%;

    padding: 16px 10px;

    border: none;
    border-radius: 20px;

    background: #efb08a;

    cursor: pointer;

    font-size: 16px;
}

.booking-button i {
    display: block;
    font-size: 27px;
    margin-bottom: 6px;
}


/* ================================================= */
/* ABOUT */
/* ================================================= */

.about-section {
    margin: 120px 0;
}

.about-text {
    padding-left: 30px;
}

.about-text h1 {
    font-family: "Ubuntu", sans-serif;

    font-size: clamp(45px, 5vw, 70px);

    font-weight: 400;
}

.about-text p {
    color: gray;

    margin-top: 30px;

    line-height: 1.6;
}

.about-image {
    width: 100%;
    height: 350px;

    object-fit: cover;

    border-radius: 10px;
}

.experience-card {
    width: 100%;
}

.experience {
    min-height: 130px;

    background: #282828;

    border-radius: 10px;

    text-align: center;

    padding: 28px;

    color: white;
}

.experience h1 {
    font-size: 40px;
}

.experience-image {
    height: 205px;
    margin-top: 10px;
}

.experience-image img {
    width: 100%;
    height: 100%;

    object-fit: cover;

    border-radius: 10px;
}


/* ================================================= */
/* OFFER */
/* ================================================= */

.offer-section {
    margin-top: 100px;
}

.offer-content {
    min-height: 300px;

    background: #425a4d;

    color: white;

    padding: 60px 50px;
}

.offer-content h1 {
    font-family: "Ubuntu", sans-serif;

    font-size: clamp(40px, 4vw, 50px);

    font-weight: 300;

    margin-bottom: 20px;
}

.offer-content h3 {
    font-size: 23px;

    font-weight: 400;

    margin-bottom: 10px;
}

.offer-content p {
    font-size: 20px;
    margin-bottom: 30px;
}

.offer-content span {
    color: #ddd;
}

.offer-content button {
    border: none;

    border-radius: 20px;

    padding: 10px 15px;

    background: #c97e5f;

    color: white;

    font-size: 17px;
}

.offer-image {
    height: 300px;
    background: #2e3b34;
}

.offer-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}


/* ================================================= */
/* SLIDER */
/* ================================================= */

.slider-section {
    margin-top: 50px;
}

.mySwiper {
    width: 100%;
    height: 500px;
}

.swiper-slide {
    border-radius: 5px;
    overflow: hidden;
}

.swiper-slide img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}


/* ================================================= */
/* VEHICLES */
/* ================================================= */

.vehicles-section {
    margin: 50px 0;

    background: #ece7e4;

    padding: 50px 0;
}

.section-title {
    font-size: clamp(32px, 4vw, 40px);
    margin-bottom: 20px;
}

.vehicle-card {
    height: 255px;

    background: white;

    border-radius: 20px;

    overflow: hidden;

    transition: 0.5s;
}

.vehicle-card:hover {
    transform: translateY(-5px);

    box-shadow:
        rgba(0, 0, 0, 0.2) 0px 12px 28px,
        rgba(0, 0, 0, 0.1) 0px 2px 4px;
}

.vehicle-info {
    height: 50%;
    padding: 10px 20px;
}

.vehicle-info h2 {
    font-size: 19px;
    font-weight: 500;
    margin-bottom: 4px;
}

.vehicle-info p {
    font-weight: 300;
}

.vehicle-info span {
    color: gray;
}

.vehicle-image {
    height: 50%;
    overflow: hidden;
}

.vehicle-image img {
    width: 100%;
    height: 100%;

    object-fit: cover;

    transition: 0.7s;
}

.vehicle-card:hover .vehicle-image img {
    transform: scale(1.1);
}


/* ================================================= */
/* FOOTER */
/* ================================================= */

.footer {
    background: #111;

    color: #ccc;

    padding: 50px 0 20px;
}

.footer-logo {
    font-size: 40px;

    color: #c97e5f;

    font-family: "Ubuntu", sans-serif;

    font-weight: 500;
}

.footer h3 {
    font-size: 16px;

    color: white;

    margin-bottom: 15px;
}

.footer p {
    line-height: 1.6;
}

.footer ul {
    padding: 0;
    list-style: none;
}

.footer ul li {
    margin-bottom: 8px;
}

.footer a {
    color: #ccc;
    text-decoration: none;
}

.footer a:hover {
    color: #c97e5f;
}

.social-icons {
    margin-top: 15px;
}

.social-icons a {
    display: inline-flex;

    align-items: center;
    justify-content: center;

    width: 35px;
    height: 35px;

    margin-right: 5px;

    border-radius: 4px;

    background: #333;
}

.social-icons a:hover {
    background: #c97e5f;
    color: white;
}

.footer-bottom {
    text-align: center;

    padding-top: 20px;

    margin-top: 30px;

    font-size: 12px;

    color: #777;

    border-top: 1px solid #333;
}


/* ================================================= */
/* TABLET */
/* ================================================= */

@media (max-width: 991px) {

    .navbar {
        background: rgba(0, 0, 0, 0.85);
        padding: 12px 0;
    }

    .navbar-collapse {
        padding: 20px 0;
    }

    .navbar-nav {
        text-align: center;
    }

    .navbar-brand {
        margin: 0 auto;
    }

    .navbar-right {
        justify-content: center;
        margin-top: 15px;
    }

    .hero-section {
        min-height: 700px;
    }

    .hero-title {
        font-size: 55px;
    }

    .booking-wrapper {
        bottom: -170px;

        width: 90%;

        padding: 20px 25px;
    }

    .booking-item {
        border-right: none;
        border-bottom: 1px solid #ddd;

        padding: 15px 0;
    }

    .about-section {
        margin-top: 230px;
    }

    .about-text {
        padding-left: 0;
    }

    .offer-content {
        padding: 50px;
    }

    .mySwiper {
        height: 400px;
    }

    .vehicle-card {
        height: 270px;
    }

}


/* ================================================= */
/* MOBILE */
/* ================================================= */

@media (max-width: 576px) {

    .navbar {
        padding: 10px 15px;
    }

    .navbar-brand {
        font-size: 25px;
    }

    .nav-link {
        font-size: 16px;
    }

    .hero-section {
        min-height: 650px;
    }

    .hero-title {
        font-size: 42px;
    }

    .btn-banner {
        font-size: 15px;
    }

    .booking-wrapper {
        width: 94%;
        bottom: -300px;

        padding: 20px;
    }

    .booking-item {
        padding: 12px 0;
    }

    .booking-item h3 {
        font-size: 16px;
    }

    .booking-item p {
        font-size: 14px;
        margin-top: 8px;
    }

    .booking-button {
        margin-top: 15px;
    }

    .about-section {
        margin-top: 360px;
        margin-bottom: 70px;
    }

    .about-text {
        padding: 0;
    }

    .about-text h1 {
        font-size: 48px;
    }

    .about-text p {
        margin-top: 20px;
        font-size: 15px;
    }

    .about-image {
        height: 280px;
    }

    .experience h1 {
        font-size: 34px;
    }

    .experience-image {
        height: 220px;
    }

    .offer-section {
        margin-top: 50px;
    }

    .offer-content {
        padding: 40px 25px;
    }

    .offer-content h1 {
        font-size: 40px;
    }

    .offer-content h3 {
        font-size: 20px;
    }

    .offer-image {
        height: 250px;
    }

    .slider-section {
        margin-top: 40px;
    }

    .mySwiper {
        height: 280px;
    }

    .vehicles-section {
        margin-top: 40px;
        padding: 40px 0;
    }

    .vehicle-card {
        height: 270px;
    }

    .footer {
        padding: 40px 0 20px;
    }

    .footer-logo {
        font-size: 35px;
    }

}


/* ================================================= */
/* VERY SMALL PHONE */
/* ================================================= */

@media (max-width: 375px) {

    .hero-title {
        font-size: 36px;
    }

    .booking-wrapper {
        bottom: -315px;
    }

    .about-section {
        margin-top: 380px;
    }

    .about-text h1 {
        font-size: 42px;
    }

    .mySwiper {
        height: 230px;
    }

}
</style>