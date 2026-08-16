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
import experienceImage from '../assets/images/rolls-royce-boat-tail.jpg'
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

            <div class="container position-relative">

                <!-- BRAND — always visible -->
                <a href="#" class="navbar-brand">
                    RenC<span>.</span>
                </a>

                <!-- MOBILE BUTTON -->
                <button class="navbar-toggler ms-auto" type="button" data-bs-toggle="collapse"
                    data-bs-target="#mainNavbar" aria-controls="mainNavbar" aria-expanded="false"
                    aria-label="Toggle navigation">
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

                    <!-- RIGHT -->
                    <div class="navbar-right d-flex align-items-center ms-lg-auto">

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
            <div class="container hero-content text-center text-lg-start">
                <h1 class="hero-title" data-aos="fade-up">
                    Luxury car<br>rental
                </h1>
                <button class="btn-banner" data-aos="fade-up" data-aos-delay="200">
                    Rent now
                </button>
            </div>

            <!-- BOOKING WIDGET -->
            <div class="booking-container">
                <div class="container">
                    <div class="booking-wrapper">
                        <div class="row align-items-center g-0">
                            <div class="col-lg-3 col-md-4 booking-item">
                                <div class="booking-content">
                                    <h3>Pick Up Address</h3>
                                    <p>From: address, airport...</p>
                                </div>
                            </div>
                            <div class="col-lg-3 col-md-4 booking-item">
                                <div class="booking-content">
                                    <h3>Pick Up Date</h3>
                                    <p>JUN 11, 2025</p>
                                </div>
                            </div>
                            <div class="col-lg-3 col-md-4 booking-item">
                                <div class="booking-content">
                                    <h3>Pick Up Time</h3>
                                    <p>12:00 AM</p>
                                </div>
                            </div>
                            <div class="col-lg-3 col-12">
                                <button class="booking-button">
                                    <i class="bi bi-calendar3 d-none d-lg-inline"></i>
                                    <span>Book Now</span>
                                </button>
                            </div>
                        </div>
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
                    <div class="col-lg-4 order-2 order-lg-1">

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
                    <div class="col-lg-4 order-1 order-lg-2">

                        <div class="about-image-wrapper" data-aos="fade-right">

                            <img :src="aboutImage" class="about-image" alt="Luxury vehicle">

                        </div>

                    </div>

                    <!-- EXPERIENCE -->
                    <div class="col-lg-4 order-3">

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

                    <div class="col-lg-6 order-2 order-lg-1">

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

                    <div class="col-lg-6 order-1 order-lg-2">

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

                        <img :src="slide" alt="Luxury car" loading="lazy">

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

                                <img :src="vehicle.image" :alt="vehicle.name" loading="lazy">

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

                        <a href="#" aria-label="YouTube">
                            <i class="bi bi-youtube"></i>
                        </a>

                        <a href="#" aria-label="Facebook">
                            <i class="bi bi-facebook"></i>
                        </a>

                        <a href="#" aria-label="Twitter">
                            <i class="bi bi-twitter-x"></i>
                        </a>

                        <a href="#" aria-label="Instagram">
                            <i class="bi bi-instagram"></i>
                        </a>

                        <a href="#" aria-label="LinkedIn">
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
/* BASE */
/* ================================================= */

html {
    scroll-behavior: smooth;
}

img {
    max-width: 100%;
    height: auto;
}

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
    transition: background 0.3s, padding 0.3s;
}

.navbar-brand {
    color: white;
    font-size: 30px;
    font-weight: 700;
    font-family: "Ubuntu", sans-serif;
    z-index: 2;
}

.navbar-brand:hover {
    color: white;
}

.navbar-brand span {
    color: #c97e5f;
}

.nav-link {
    color: white !important;
    font-size: 17px;
    padding: 8px 14px !important;
    transition: color 0.3s;
}

.nav-link:hover,
.nav-link:focus {
    color: #c97e5f !important;
}

.navbar-toggler {
    background: white;
    border: none;
    padding: 6px 10px;
}

.navbar-toggler:focus {
    box-shadow: 0 0 0 3px rgba(201, 126, 95, 0.4);
}

.navbar-right {
    gap: 10px;
}

.btn-navbar {
    padding: 6px 16px;
    border: 1px solid #777;
    border-radius: 6px;
    background: transparent;
    color: white;
    font-size: 15px;
    transition: all 0.3s;
    cursor: pointer;
}

.btn-navbar:hover {
    border-color: #c97e5f;
    color: #c97e5f;
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
    transition: transform 0.3s, background 0.3s;
}

.link-profile:hover i {
    transform: scale(1.05);
    background: #c97e5f;
    color: white;
}

/* Desktop: center brand absolutely */
@media (min-width: 992px) {
    .navbar>.container {
        position: relative;
    }

    .navbar-brand {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
    }

    .navbar-collapse {
        width: 100%;
        justify-content: space-between;
    }

    .navbar-nav {
        margin-right: auto !important;
    }

    .navbar-right {
        margin-left: auto;
    }
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
    padding-top: 90px;
    /* clears fixed navbar */
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
    font-size: clamp(40px, 6vw, 70px);
    font-weight: 300;
    line-height: 1.1;
    margin-bottom: 24px;
}

.btn-banner {
    background: #c97e5f;
    border: none;
    border-radius: 10px;
    color: white;
    font-size: 17px;
    padding: 12px 28px;
    transition: 0.4s;
    cursor: pointer;
}

.btn-banner:hover,
.btn-banner:focus {
    background: #b56a4b;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(201, 126, 95, 0.3);
}


/* ================================================= */
/* BOOKING */
/* ================================================= */

.booking-wrapper {
    position: absolute;
    z-index: 10;
    left: 50%;
    bottom: -35px;
    transform: translateX(-50%);
    width: min(1200px, 92%);
    background: white;
    padding: 28px 35px;
    border-radius: 8px;
    box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
}

.booking-item {
    border-right: 1px solid #e0e0e0;
    padding: 0 20px;
}

.booking-item:first-child {
    padding-left: 0;
}

.booking-item:last-of-type {
    border-right: none;
}

.booking-content h3 {
    font-size: 16px;
    color: #888;
    font-weight: 400;
    margin-bottom: 6px;
}

.booking-content p {
    font-family: "Poppins", sans-serif;
    font-size: 15px;
    color: #222;
    margin: 0;
}

.booking-button {
    width: 100%;
    padding: 16px 10px;
    border: none;
    border-radius: 20px;
    background: #efb08a;
    cursor: pointer;
    font-size: 16px;
    color: #222;
    transition: 0.3s;
}

.booking-button:hover,
.booking-button:focus {
    background: #e09e70;
    transform: translateY(-1px);
}

.booking-button i {
    display: block;
    font-size: 26px;
    margin-bottom: 6px;
}


/* ================================================= */
/* ABOUT */
/* ================================================= */

.about-section {
    margin: 110px 0 120px;
}

.about-text {
    padding-left: 20px;
}

.about-text h1 {
    font-family: "Ubuntu", sans-serif;
    font-size: clamp(42px, 5vw, 70px);
    font-weight: 400;
}

.about-text p {
    color: #666;
    margin-top: 24px;
    line-height: 1.7;
    font-size: 16px;
}

.about-image {
    width: 100%;
    height: 350px;
    object-fit: cover;
    border-radius: 12px;
}

.experience-card {
    width: 100%;
}

.experience {
    min-height: 130px;
    background: #282828;
    border-radius: 12px;
    text-align: center;
    padding: 28px;
    color: white;
}

.experience h1 {
    font-size: 40px;
    font-weight: 600;
}

.experience-image {
    height: 205px;
    margin-top: 12px;
    border-radius: 12px;
    overflow: hidden;
}

.experience-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 12px;
    transition: transform 0.6s;
}

.experience-image:hover img {
    transform: scale(1.05);
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
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.offer-content h1 {
    font-family: "Ubuntu", sans-serif;
    font-size: clamp(36px, 4vw, 50px);
    font-weight: 300;
    margin-bottom: 20px;
}

.offer-content h3 {
    font-size: 22px;
    font-weight: 400;
    margin-bottom: 10px;
}

.offer-content p {
    font-size: 20px;
    margin-bottom: 30px;
}

.offer-content span {
    color: #ddd;
    font-size: 16px;
}

.offer-content button {
    border: none;
    border-radius: 20px;
    padding: 12px 24px;
    background: #c97e5f;
    color: white;
    font-size: 16px;
    cursor: pointer;
    align-self: flex-start;
    transition: 0.3s;
}

.offer-content button:hover,
.offer-content button:focus {
    background: #b56a4b;
    transform: translateY(-2px);
}

.offer-image {
    height: 300px;
    background: #2e3b34;
    overflow: hidden;
}

.offer-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.6s;
}

.offer-image:hover img {
    transform: scale(1.05);
}


/* ================================================= */
/* SLIDER */
/* ================================================= */

.slider-section {
    margin-top: 50px;
}

.mySwiper {
    width: 100%;
    aspect-ratio: 16 / 7;
    max-height: 520px;
    border-radius: 8px;
    overflow: hidden;
}

.swiper-slide {
    border-radius: 8px;
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
    padding: 60px 0;
}

.section-title {
    font-family: "Ubuntu", sans-serif;
    font-size: clamp(30px, 4vw, 40px);
    margin-bottom: 30px;
    font-weight: 500;
}

.vehicle-card {
    min-height: 260px;
    background: white;
    border-radius: 20px;
    overflow: hidden;
    transition: 0.5s;
    display: flex;
    flex-direction: column;
}

.vehicle-card:hover {
    transform: translateY(-6px);
    box-shadow:
        rgba(0, 0, 0, 0.2) 0px 12px 28px,
        rgba(0, 0, 0, 0.1) 0px 2px 4px;
}

.vehicle-info {
    padding: 18px 20px;
    flex: 1;
}

.vehicle-info h2 {
    font-size: 18px;
    font-weight: 500;
    margin-bottom: 6px;
    line-height: 1.3;
}

.vehicle-info p {
    font-weight: 300;
    font-size: 15px;
    margin: 0;
}

.vehicle-info span {
    color: #888;
    font-size: 13px;
}

.vehicle-image {
    height: 160px;
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
    color: #bbb;
    padding: 60px 0 20px;
}

.footer-logo {
    font-size: 40px;
    color: #c97e5f;
    font-family: "Ubuntu", sans-serif;
    font-weight: 500;
    margin-bottom: 16px;
}

.footer h3 {
    font-size: 16px;
    color: white;
    margin-bottom: 18px;
    font-weight: 500;
}

.footer p {
    line-height: 1.7;
    font-size: 15px;
}

.footer ul {
    padding: 0;
    list-style: none;
    margin: 0;
}

.footer ul li {
    margin-bottom: 10px;
}

.footer a {
    color: #bbb;
    text-decoration: none;
    font-size: 15px;
    transition: color 0.3s;
}

.footer a:hover,
.footer a:focus {
    color: #c97e5f;
}

.social-icons {
    margin-top: 18px;
    display: flex;
    gap: 8px;
}

.social-icons a {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 38px;
    height: 38px;
    border-radius: 6px;
    background: #333;
    color: #ccc;
    font-size: 16px;
    transition: 0.3s;
}

.social-icons a:hover,
.social-icons a:focus {
    background: #c97e5f;
    color: white;
    transform: translateY(-2px);
}

.footer-bottom {
    text-align: center;
    padding-top: 24px;
    margin-top: 40px;
    font-size: 13px;
    color: #777;
    border-top: 1px solid #333;
}


/* ================================================= */
/* TABLET (≤991px) */
/* ================================================= */

@media (max-width: 991px) {

    .navbar {
        background: rgba(0, 0, 0, 0.9);
        padding: 12px 0;
    }

    .navbar-collapse {
        background: rgba(0, 0, 0, 0.95);
        padding: 15px;
        border-radius: 10px;
        margin-top: 10px;
    }

    .navbar-nav {
        text-align: center;
        padding: 10px 0;
    }

    .nav-link {
        padding: 12px !important;
        font-size: 16px;
    }

    .navbar-right {
        justify-content: center;
        padding: 10px 0;
    }

    .hero-section {
        min-height: 700px;
        padding-top: 80px;
    }

    .hero-title {
        font-size: 55px;
    }

    /* Booking becomes part of document flow with negative margin overlap */
    .booking-wrapper {
        position: relative;
        left: auto;
        bottom: auto;
        transform: none;
        margin: -70px auto 0;
        width: 94%;
        padding: 22px 25px;
    }

    .booking-item {
        border-right: none;
        border-bottom: 1px solid #eee;
        padding: 14px 0;
    }

    .booking-item:last-child {
        border-bottom: none;
    }

    .booking-content h3 {
        font-size: 15px;
    }

    .booking-content p {
        font-size: 14px;
    }

    .about-section {
        margin: 60px 0;
    }

    .about-text {
        padding-left: 0;
        text-align: center;
    }

    .about-image {
        height: 320px;
    }

    .experience h1 {
        font-size: 36px;
    }

    .experience-image {
        height: 220px;
    }

    .offer-section {
        margin-top: 60px;
    }

    .offer-content {
        padding: 50px 40px;
        min-height: auto;
    }

    .offer-image {
        height: 350px;
    }

    .mySwiper {
        aspect-ratio: 16 / 9;
        max-height: 420px;
    }

    .vehicle-card {
        min-height: 280px;
    }

    .vehicle-image {
        height: 180px;
    }
}


/* ================================================= */
/* MOBILE (≤576px) */
/* ================================================= */

@media (max-width: 576px) {

    .navbar {
        padding: 10px 0;
    }

    .navbar-brand {
        font-size: 26px;
    }

    .nav-link {
        font-size: 15px;
    }

    .hero-section {
        min-height: 600px;
        padding-top: 70px;
    }

    .hero-title {
        font-size: 42px;
    }

    .btn-banner {
        font-size: 15px;
        padding: 10px 22px;
    }

    .booking-wrapper {
        width: 95%;
        margin-top: -50px;
        padding: 18px;
    }

    .booking-item {
        padding: 12px 0;
    }

    .booking-item h3 {
        font-size: 14px;
    }

    .booking-item p {
        font-size: 13px;
        margin-top: 4px;
    }

    .booking-button {
        margin-top: 10px;
        padding: 14px 10px;
        font-size: 15px;
    }

    .about-section {
        margin: 40px 0;
    }

    .about-text h1 {
        font-size: 42px;
    }

    .about-text p {
        margin-top: 16px;
        font-size: 15px;
    }

    .about-image {
        height: 260px;
    }

    .experience h1 {
        font-size: 32px;
    }

    .experience-image {
        height: 200px;
    }

    .offer-section {
        margin-top: 40px;
    }

    .offer-content {
        padding: 40px 25px;
    }

    .offer-content h1 {
        font-size: 36px;
    }

    .offer-content h3 {
        font-size: 19px;
    }

    .offer-image {
        height: 260px;
    }

    .slider-section {
        margin-top: 40px;
    }

    .mySwiper {
        aspect-ratio: 4 / 3;
        max-height: 320px;
    }

    .vehicles-section {
        margin-top: 40px;
        padding: 40px 0;
    }

    .section-title {
        margin-bottom: 24px;
    }

    .vehicle-card {
        min-height: 260px;
    }

    .vehicle-info h2 {
        font-size: 17px;
    }

    .vehicle-image {
        height: 150px;
    }

    .footer {
        padding: 40px 0 20px;
    }

    .footer-logo {
        font-size: 34px;
    }

    .footer h3 {
        margin-bottom: 14px;
    }

    .footer .col-lg-4,
    .footer .col-lg-2 {
        margin-bottom: 10px;
    }
}


/* ================================================= */
/* VERY SMALL PHONE (≤375px) */
/* ================================================= */

@media (max-width: 375px) {

    .hero-title {
        font-size: 36px;
    }

    .booking-wrapper {
        margin-top: -45px;
        padding: 16px;
    }

    .about-text h1 {
        font-size: 38px;
    }

    .mySwiper {
        max-height: 260px;
    }

    .vehicle-card {
        min-height: 240px;
    }
}
</style>