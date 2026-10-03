# Anuskaaa
<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For Lui — Anuska</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>

/* =========================================================
   ROOT
========================================================= */

:root{

    --black:#020202;
    --black2:#080506;

    --burgundy:#19070c;
    --burgundy2:#3a1019;

    --gold:#d7b36a;
    --gold2:#f3dda4;

    --cream:#eee4d0;
    --white:#fff8eb;

    --text:#bcb1a3;
    --muted:#71675e;

    --line:rgba(215,179,106,.20);

}


/* =========================================================
   RESET
========================================================= */

*{

    margin:0;
    padding:0;
    box-sizing:border-box;

}

html{

    scroll-behavior:smooth;

}

body{

    background:

        radial-gradient(
            circle at 50% -10%,
            rgba(100,22,40,.42),
            transparent 35%
        ),

        linear-gradient(
            180deg,
            #020202 0%,
            #080506 40%,
            #020202 100%
        );

    color:var(--text);

    font-family:"DM Sans",sans-serif;

    overflow-x:hidden;

}


/* =========================================================
   CINEMATIC GRAIN
========================================================= */

body::before{

    content:"";

    position:fixed;

    inset:0;

    z-index:9998;

    pointer-events:none;

    opacity:.035;

    background-image:url(
        "data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.5'/%3E%3C/svg%3E"
    );

}


/* =========================================================
   FLOWING SPARKLES
========================================================= */

#sparkleField{

    position:fixed;

    inset:0;

    z-index:3;

    pointer-events:none;

    overflow:hidden;

}


.sparkle{

    position:absolute;

    border-radius:50%;

    background:

        radial-gradient(
            circle,
            #fff9df 0%,
            #f3dda4 35%,
            rgba(215,179,106,.15) 70%,
            transparent 100%
        );

    box-shadow:

        0 0 5px
        rgba(255,239,188,.9),

        0 0 14px
        rgba(215,179,106,.55),

        0 0 28px
        rgba(215,179,106,.18);

    animation:

        sparkleFlow
        linear
        infinite;

}


@keyframes sparkleFlow{

    0%{

        transform:
            translate3d(
                var(--startX),
                110vh,
                0
            )
            scale(.35);

        opacity:0;

    }

    8%{

        opacity:var(--opacity);

    }

    50%{

        transform:
            translate3d(
                var(--midX),
                50vh,
                0
            )
            scale(1);

    }

    92%{

        opacity:var(--opacity);

    }

    100%{

        transform:
            translate3d(
                var(--endX),
                -15vh,
                0
            )
            scale(.25);

        opacity:0;

    }

}


/* =========================================================
   MUSIC — TOP
========================================================= */

.music-section{

    position:relative;

    z-index:20;

    width:100%;

    padding:
        16px 20px
        18px;

    text-align:center;

    background:

        linear-gradient(
            180deg,
            rgba(2,2,2,.99),
            rgba(12,5,7,.97)
        );

    border-bottom:
        1px solid
        rgba(215,179,106,.25);

    box-shadow:
        0 10px 40px
        rgba(0,0,0,.5);

    backdrop-filter:blur(20px);

}


.music-title{

    margin-bottom:6px;

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:20px;

    letter-spacing:3px;

}


.music-subtitle{

    margin-bottom:10px;

    color:#6e665d;

    font-size:8px;

    letter-spacing:4px;

    text-transform:uppercase;

}


.music-section audio{

    width:min(520px,94%);

    height:36px;

}


/* =========================================================
   GENERAL
========================================================= */

section{

    position:relative;

    z-index:5;

    padding:
        130px 7%;

}


.container{

    max-width:1200px;

    margin:auto;

}


h1,h2,h3,h4{

    font-family:
        "Cormorant Garamond",
        serif;

    color:var(--cream);

    font-weight:500;

}


h2{

    font-size:
        clamp(
            48px,
            8vw,
            105px
        );

    line-height:.88;

}


p{

    line-height:1.9;

}


.gold{

    color:var(--gold2);

}


.eyebrow{

    margin-bottom:20px;

    color:var(--gold);

    font-size:9px;

    letter-spacing:6px;

    text-transform:uppercase;

}


.center{

    text-align:center;

}


.btn{

    display:inline-flex;

    align-items:center;

    justify-content:center;

    min-height:52px;

    padding:0 30px;

    border:
        1px solid
        rgba(215,179,106,.65);

    background:
        rgba(215,179,106,.025);

    color:var(--gold2);

    text-decoration:none;

    font-size:10px;

    letter-spacing:3px;

    text-transform:uppercase;

    transition:.4s ease;

}


.btn:hover{

    background:var(--gold);

    color:#070504;

    transform:translateY(-3px);

    box-shadow:
        0 0 45px
        rgba(215,179,106,.2);

}


/* =========================================================
   REVEAL
========================================================= */

.reveal{

    opacity:0;

    transform:
        translateY(45px);

    transition:
        1.15s
        cubic-bezier(.2,.7,.2,1);

}


.reveal.visible{

    opacity:1;

    transform:
        translateY(0);

}


/* =========================================================
   HERO
========================================================= */

.hero{

    min-height:
        calc(100vh - 95px);

    display:flex;

    align-items:center;

    justify-content:center;

    text-align:center;

    overflow:hidden;

}


.hero::before{

    content:"";

    position:absolute;

    width:850px;

    height:850px;

    border-radius:50%;

    background:

        radial-gradient(
            circle,
            rgba(95,20,39,.38),
            transparent 68%
        );

    filter:blur(25px);

}


.hero-content{

    position:relative;

    max-width:1100px;

}


.hero-small{

    margin-bottom:35px;

    color:var(--gold);

    font-size:10px;

    letter-spacing:8px;

}


.hero h1{

    margin-bottom:42px;

    font-size:
        clamp(
            72px,
            13vw,
            175px
        );

    line-height:.69;

}


.hero-line{

    display:block;

}


.hero-description{

    max-width:680px;

    margin:
        0 auto 40px;

    color:#aaa093;

    font-size:15px;

}


.hero-name{

    margin-top:40px;

    color:#746b62;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:23px;

    letter-spacing:4px;

}


.hero-name strong{

    color:var(--gold2);

    font-weight:500;

}


.scroll-text{

    position:absolute;

    bottom:25px;

    left:50%;

    transform:translateX(-50%);

    color:#5c554d;

    font-size:8px;

    letter-spacing:5px;

}


/* =========================================================
   INTRO
========================================================= */

.intro{

    background:

        linear-gradient(
            180deg,
            transparent,
            rgba(38,8,15,.40),
            transparent
        );

}


.big-text{

    max-width:950px;

    margin:
        60px auto 0;

    text-align:center;

    color:#d1c5b5;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(
            30px,
            4.5vw,
            52px
        );

    line-height:1.3;

}


.big-text span{

    color:var(--gold2);

}


/* =========================================================
   COUNTDOWN
========================================================= */

.countdown-section{

    min-height:80vh;

    display:flex;

    align-items:center;

}


.countdown-box{

    position:relative;

    max-width:1050px;

    margin:auto;

    padding:
        90px 50px;

    text-align:center;

    background:

        radial-gradient(
            circle at 50% 0%,
            rgba(100,25,43,.40),
            transparent 58%
        ),

        rgba(7,4,5,.82);

    border:
        1px solid
        var(--line);

    box-shadow:
        0 35px 100px
        rgba(0,0,0,.6);

}


.countdown-box::before{

    content:"";

    position:absolute;

    inset:15px;

    border:
        1px solid
        rgba(215,179,106,.06);

}


.countdown-title{

    margin-bottom:25px;

    font-size:
        clamp(
            48px,
            7vw,
            90px
        );

}


.countdown-description{

    max-width:600px;

    margin:
        0 auto 55px;

    color:#8f857a;

}


.countdown{

    display:flex;

    justify-content:center;

    flex-wrap:wrap;

    gap:45px;

    margin-bottom:45px;

}


.time{

    min-width:95px;

}


.time strong{

    display:block;

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:60px;

    font-weight:500;

    line-height:1;

}


.time small{

    color:#655d55;

    font-size:8px;

    letter-spacing:4px;

}


/* =========================================================
   HER
========================================================= */

.her{

    text-align:center;

}


.her-card{

    max-width:1000px;

    margin:
        65px auto 0;

    padding:
        100px 30px;

    border-top:
        1px solid var(--line);

    border-bottom:
        1px solid var(--line);

}


.her-name{

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(
            80px,
            16vw,
            180px
        );

    line-height:.72;

}


.nickname{

    margin-top:30px;

    color:#756c62;

    font-size:10px;

    letter-spacing:8px;

    text-transform:uppercase;

}


.her-quote{

    max-width:700px;

    margin:
        50px auto 0;

    color:#c7bbaa;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(
            27px,
            4vw,
            43px
        );

    line-height:1.25;

}


/* =========================================================
   LETTER
========================================================= */

.letter-section{

    background:

        linear-gradient(
            180deg,
            transparent,
            rgba(30,7,13,.42),
            transparent
        );

}


.letter{

    max-width:900px;

    margin:
        65px auto 0;

    padding:
        75px 65px;

    background:

        linear-gradient(
            135deg,
            rgba(29,8,13,.88),
            rgba(5,4,4,.94)
        );

    border:
        1px solid var(--line);

    box-shadow:
        0 40px 100px
        rgba(0,0,0,.5);

}


.letter-header{

    display:flex;

    justify-content:space-between;

    padding-bottom:20px;

    margin-bottom:45px;

    border-bottom:
        1px solid var(--line);

    color:#665e56;

    font-size:8px;

    letter-spacing:4px;

}


.letter h3{

    margin-bottom:35px;

    font-size:54px;

}


.letter p{

    margin-bottom:25px;

    color:#aaa093;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:21px;

    line-height:1.7;

}


.signature{

    margin-top:45px;

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:36px;

}


/* =========================================================
   REASONS
========================================================= */

.reasons-grid{

    display:grid;

    grid-template-columns:
        repeat(3,1fr);

    gap:15px;

    margin-top:65px;

}


.reason{

    min-height:245px;

    padding:35px;

    border:
        1px solid var(--line);

    background:
        rgba(255,255,255,.012);

    transition:.45s ease;

}


.reason:hover{

    transform:
        translateY(-8px);

    border-color:
        rgba(215,179,106,.6);

    background:
        rgba(215,179,106,.025);

}


.reason-number{

    margin-bottom:35px;

    color:var(--gold);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:34px;

}


.reason h3{

    margin-bottom:12px;

    font-size:31px;

}


.reason p{

    color:#7f766c;

    font-size:12px;

    line-height:1.7;

}


/* =========================================================
   MEMORY WALL
========================================================= */

.memory-section{

    background:

        radial-gradient(
            circle at 50% 50%,
            rgba(60,13,24,.30),
            transparent 60%
        );

}


.memory-grid{

    display:grid;

    grid-template-columns:
        repeat(2,1fr);

    gap:20px;

    margin-top:65px;

}


.memory-card{

    position:relative;

    min-height:330px;

    padding:45px;

    display:flex;

    flex-direction:column;

    justify-content:flex-end;

    overflow:hidden;

    border:
        1px solid var(--line);

    background:

        linear-gradient(
            145deg,
            rgba(39,10,17,.80),
            rgba(5,4,4,.95)
        );

}


.memory-card::after{

    content:"";

    position:absolute;

    width:260px;

    height:260px;

    right:-120px;

    top:-120px;

    border-radius:50%;

    background:

        radial-gradient(
            circle,
            rgba(215,179,106,.12),
            transparent 70%
        );

}


.memory-number{

    position:absolute;

    top:30px;

    left:35px;

    color:#5d554d;

    font-size:8px;

    letter-spacing:4px;

}


.memory-card h3{

    position:relative;

    margin-bottom:12px;

    font-size:43px;

}


.memory-card p{

    position:relative;

    max-width:500px;

    color:#81776d;

    font-size:12px;

}


/* =========================================================
   TIMELINE
========================================================= */

.timeline{

    max-width:950px;

    margin:
        65px auto 0;

}


.timeline-item{

    display:grid;

    grid-template-columns:
        120px 1fr;

    gap:35px;

    padding:
        38px 0;

    border-bottom:
        1px solid var(--line);

}


.timeline-number{

    color:var(--gold);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:34px;

}


.timeline-item h3{

    margin-bottom:8px;

    font-size:34px;

}


.timeline-item p{

    color:#81786d;

    font-size:13px;

}


/* =========================================================
   PROMISE
========================================================= */

.promise{

    text-align:center;

}


.promise-box{

    max-width:950px;

    margin:auto;

    padding:
        90px 30px;

    border-top:
        1px solid var(--line);

    border-bottom:
        1px solid var(--line);

}


.promise-box h3{

    font-size:
        clamp(
            40px,
            6vw,
            72px
        );

    line-height:1;

}


.promise-box p{

    max-width:650px;

    margin:
        35px auto 0;

    color:#8e857a;

}


/* =========================================================
   SECRET VAULT
========================================================= */

.secret{

    min-height:80vh;

    display:flex;

    align-items:center;

    text-align:center;

}


.secret-box{

    max-width:950px;

    width:100%;

    margin:auto;

    padding:
        95px 40px;

    border:
        1px solid
        rgba(215,179,106,.28);

    background:

        radial-gradient(
            circle at center,
            rgba(80,17,31,.38),
            transparent 65%
        );

}


.secret-symbol{

    width:72px;

    height:72px;

    margin:
        0 auto 30px;

    display:flex;

    align-items:center;

    justify-content:center;

    border:
        1px solid
        rgba(215,179,106,.45);

    border-radius:50%;

    color:var(--gold2);

    font-size:24px;

}


.secret-box h2{

    margin-bottom:25px;

}


.secret-box p{

    max-width:600px;

    margin:
        0 auto 35px;

    color:#80766c;

}


#secretMessage{

    display:none;

    max-width:700px;

    margin:
        45px auto 0;

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(
            28px,
            4vw,
            46px
        );

    line-height:1.3;

}


#secretMessage.show{

    display:block;

    animation:
        secretReveal 1.3s ease;

}


@keyframes secretReveal{

    from{

        opacity:0;

        transform:
            translateY(30px)
            scale(.97);

    }

    to{

        opacity:1;

        transform:
            translateY(0)
            scale(1);

    }

}


/* =========================================================
   FINAL LETTER
========================================================= */

.final-letter{

    text-align:center;

}


.final-message{

    max-width:900px;

    margin:
        60px auto 0;

    color:#d2c6b5;

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:
        clamp(
            31px,
            5vw,
            58px
        );

    line-height:1.2;

}


.final-message span{

    color:var(--gold2);

}


/* =========================================================
   FINAL
========================================================= */

.final{

    min-height:95vh;

    display:flex;

    align-items:center;

    justify-content:center;

    text-align:center;

    background:

        radial-gradient(
            circle at 50% 50%,
            rgba(92,18,37,.38),
            transparent 60%
        );

}


.final-content{

    max-width:1050px;

}


.final h2{

    margin-bottom:45px;

    font-size:
        clamp(
            70px,
            13vw,
            165px
        );

    line-height:.68;

}


.final p{

    max-width:650px;

    margin:
        0 auto 40px;

    color:#958b7e;

    font-size:14px;

}


.final-name{

    margin-top:55px;

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:43px;

    letter-spacing:3px;

}


/* =========================================================
   FOOTER
========================================================= */

footer{

    position:relative;

    z-index:5;

    padding:
        55px 20px;

    text-align:center;

    border-top:
        1px solid
        rgba(215,179,106,.12);

}


footer strong{

    color:var(--gold2);

    font-family:
        "Cormorant Garamond",
        serif;

    font-size:29px;

}


footer p{

    margin-top:8px;

    color:#514b45;

    font-size:8px;

    letter-spacing:4px;

    text-transform:uppercase;

}


/* =========================================================
   TABLET
========================================================= */

@media(max-width:900px){

    .reasons-grid{

        grid-template-columns:
            repeat(2,1fr);

    }


    .memory-grid{

        grid-template-columns:1fr;

    }

}


/* =========================================================
   MOBILE
========================================================= */

@media(max-width:600px){

    section{

        padding:
            95px 6%;

    }


    .music-section{

        padding:
            13px 12px 15px;

    }


    .music-title{

        font-size:17px;

    }


    .music-subtitle{

        font-size:7px;

        letter-spacing:3px;

    }


    .hero{

        min-height:88vh;

    }


    .hero h1{

        font-size:70px;

    }


    .hero-small{

        font-size:8px;

        letter-spacing:5px;

    }


    .countdown-box{

        padding:
            65px 20px;

    }


    .countdown{

        gap:24px;

    }


    .time{

        min-width:65px;

    }


    .time strong{

        font-size:43px;

    }


    .letter{

        padding:
            50px 25px;

    }


    .letter h3{

        font-size:43px;

    }


    .letter p{

        font-size:19px;

    }


    .reasons-grid{

        grid-template-columns:1fr;

    }


    .memory-card{

        min-height:275px;

        padding:32px;

    }


    .memory-card h3{

        font-size:37px;

    }


    .timeline-item{

        grid-template-columns:
            60px 1fr;

        gap:15px;

    }


    .timeline-number{

        font-size:25px;

    }


    .timeline-item h3{

        font-size:29px;

    }


    .secret-box{

        padding:
            70px 22px;

    }


    .final h2{

        font-size:67px;

    }

}


/* =========================================================
   SMALL MOBILE
========================================================= */

@media(max-width:400px){

    .hero h1{

        font-size:58px;

    }


    .her-name{

        font-size:75px;

    }


    .countdown{

        gap:14px;

    }


    .time{

        min-width:57px;

    }


    .time strong{

        font-size:36px;

    }


    .final h2{

        font-size:57px;

    }

}

</style>

</head>


<body>


<!-- =====================================================
     FLOWING SPARKLES
===================================================== -->

<div id="sparkleField"></div>


<!-- =====================================================
     MUSIC — FIRST SECTION
===================================================== -->

<div class="music-section">

    <div class="music-title">

        ♫ Tera Naam Doon

    </div>


    <div class="music-subtitle">

        This song is for you, Lui

    </div>


    <audio
        controls
        preload="metadata"
    >

        <source
            src="tera naam doon.mp3"
            type="audio/mpeg"
        >

        Your browser does not support
        the audio element.

    </audio>

</div>


<!-- =====================================================
     HERO
===================================================== -->

<section class="hero">

    <div class="hero-content reveal">

        <div class="hero-small">

            A LITTLE UNIVERSE MADE FOR ONE GIRL

        </div>


        <h1>

            <span class="hero-line">
                FOR
            </span>

            <span class="hero-line gold">
                LUI.
            </span>

        </h1>


        <p class="hero-description">

            Not just a birthday wish.

            Not just another message.

            A little world made especially
            for Anuska — the girl I call Lui.

        </p>


        <a
            href="#beginning"
            class="btn"
        >

            ENTER YOUR STORY

        </a>


        <div class="hero-name">

            Anuska

            <strong>
                · Lui
            </strong>

        </div>

    </div>


    <div class="scroll-text">

        KEEP SCROLLING

    </div>

</section>


<!-- =====================================================
     CHAPTER 01
===================================================== -->

<section
    class="intro"
    id="beginning"
>

    <div class="container reveal">

        <div class="center">

            <div class="eyebrow">

                CHAPTER 01 · THE BEGINNING

            </div>


            <h2>

                SOME PEOPLE

                <span class="gold">
                    FEEL DIFFERENT.
                </span>

            </h2>

        </div>


        <div class="big-text">

            Somewhere between ordinary conversations,
            random laughs and countless little moments,

            <span>
                you became someone extraordinary to me.
            </span>

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 02 — COUNTDOWN
===================================================== -->

<section class="countdown-section">

    <div class="countdown-box reveal">

        <div class="eyebrow">

            CHAPTER 02 · THE MOMENT

        </div>


        <h2 class="countdown-title">

            YOUR DAY

            <span class="gold">
                IS COMING.
            </span>

        </h2>


        <p class="countdown-description">

            The countdown to the day
            that belongs completely to you.

        </p>


        <div class="countdown">

            <div class="time">

                <strong id="days">
                    00
                </strong>

                <small>
                    DAYS
                </small>

            </div>


            <div class="time">

                <strong id="hours">
                    00
                </strong>

                <small>
                    HOURS
                </small>

            </div>


            <div class="time">

                <strong id="minutes">
                    00
                </strong>

                <small>
                    MINUTES
                </small>

            </div>


            <div class="time">

                <strong id="seconds">
                    00
                </strong>

                <small>
                    SECONDS
                </small>

            </div>

        </div>


        <div class="eyebrow">

            05 · 10 · 2026

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 03 — HER
===================================================== -->

<section class="her">

    <div class="container reveal">

        <div class="eyebrow">

            CHAPTER 03 · HER

        </div>


        <h2>

            LET'S TALK ABOUT

            <span class="gold">
                HER.
            </span>

        </h2>


        <div class="her-card">

            <div class="her-name">

                Anuska

            </div>


            <div class="nickname">

                ALSO KNOWN AS · LUI

            </div>


            <div class="her-quote">

                Some people enter your life.

                Some people become
                a part of your life.

                <span class="gold">
                    You became both.
                </span>

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 04 — LETTER
===================================================== -->

<section class="letter-section">

    <div class="container">

        <div class="center reveal">

            <div class="eyebrow">

                CHAPTER 04 · A LETTER

            </div>


            <h2>

                WORDS

                <span class="gold">
                    FOR YOU.
                </span>

            </h2>

        </div>


        <div class="letter reveal">

            <div class="letter-header">

                <span>
                    PRIVATE LETTER
                </span>

                <span>
                    FOR LUI
                </span>

            </div>


            <h3>

                Dear Lui,

            </h3>


            <p>

                I don't know if a website can ever
                explain everything someone means
                to you.

            </p>


            <p>

                But I wanted to try.

            </p>


            <p>

                You are one of those people who
                quietly become a part of someone's
                everyday life and somehow make
                everything feel a little different.

            </p>


            <p>

                Your name, your little habits,
                your laugh, our random conversations
                and even the smallest moments have
                their own place in my memory.

            </p>


            <p>

                I could write hundreds of messages,
                but none of them would completely
                explain how important you are to me.

            </p>


            <p>

                So for now, I'll simply say this:

                I'm really glad that you're here.

            </p>


            <p>

                And I'm even happier that I get
                to call you Lui.

            </p>


            <div class="signature">

                — Liskun

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 05 — REASONS
===================================================== -->

<section>

    <div class="container">

        <div class="reveal">

            <div class="eyebrow">

                CHAPTER 05 · THE LITTLE THINGS

            </div>


            <h2>

                WHY YOU ARE

                <span class="gold">
                    SPECIAL.
                </span>

            </h2>

        </div>


        <div class="reasons-grid">


            <div class="reason reveal">

                <div class="reason-number">
                    01
                </div>

                <h3>
                    Your Smile
                </h3>

                <p>

                    There are smiles you notice.

                    And then there are smiles
                    you remember.

                </p>

            </div>


            <div class="reason reveal">

                <div class="reason-number">
                    02
                </div>

                <h3>
                    Your Energy
                </h3>

                <p>

                    Somehow you can make ordinary
                    moments feel completely different.

                </p>

            </div>


            <div class="reason reveal">

                <div class="reason-number">
                    03
                </div>

                <h3>
                    Your Little Things
                </h3>

                <p>

                    The tiny things you probably
                    don't even notice are often
                    the things I remember most.

                </p>

            </div>


            <div class="reason reveal">

                <div class="reason-number">
                    04
                </div>

                <h3>
                    Your Presence
                </h3>

                <p>

                    Sometimes someone doesn't need
                    to do anything special.

                    Their presence is enough.

                </p>

            </div>


            <div class="reason reveal">

                <div class="reason-number">
                    05
                </div>

                <h3>
                    Our Memories
                </h3>

                <p>

                    Every small memory becomes
                    another piece of a bigger story.

                </p>

            </div>


            <div class="reason reveal">

                <div class="reason-number">
                    06
                </div>

                <h3>
                    Simply You
                </h3>

                <p>

                    And honestly, I don't need
                    a complicated reason.

                    You're just you.

                </p>

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 06 — MEMORIES
===================================================== -->

<section class="memory-section">

    <div class="container">

        <div class="center reveal">

            <div class="eyebrow">

                CHAPTER 06 · MEMORIES

            </div>


            <h2>

                LITTLE MOMENTS.

                <span class="gold">
                    BIG MEANING.
                </span>

            </h2>

        </div>


        <div class="memory-grid">


            <div class="memory-card reveal">

                <div class="memory-number">

                    MEMORY 01

                </div>


                <h3>

                    Random Conversations

                </h3>


                <p>

                    The conversations that begin
                    with absolutely nothing and somehow
                    become the best part of the day.

                </p>

            </div>


            <div class="memory-card reveal">

                <div class="memory-number">

                    MEMORY 02

                </div>


                <h3>

                    Unexpected Laughs

                </h3>


                <p>

                    The moments where neither of us
                    planned to laugh, but somehow
                    we ended up laughing anyway.

                </p>

            </div>


            <div class="memory-card reveal">

                <div class="memory-number">

                    MEMORY 03

                </div>


                <h3>

                    Quiet Moments

                </h3>


                <p>

                    Sometimes the quietest moments
                    end up becoming the ones
                    that stay with us.

                </p>

            </div>


            <div class="memory-card reveal">

                <div class="memory-number">

                    MEMORY 04

                </div>


                <h3>

                    Everything In Between

                </h3>


                <p>

                    The story isn't only about
                    the big moments.

                    It's everything between them.

                </p>

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 07 — TIMELINE
===================================================== -->

<section>

    <div class="container">

        <div class="center reveal">

            <div class="eyebrow">

                CHAPTER 07 · OUR STORY

            </div>


            <h2>

                A STORY

                <span class="gold">
                    STILL BEING WRITTEN.
                </span>

            </h2>

        </div>


        <div class="timeline">


            <div class="timeline-item reveal">

                <div class="timeline-number">
                    01
                </div>


                <div>

                    <h3>
                        Before
                    </h3>

                    <p>

                        Two people living their own
                        ordinary days.

                    </p>

                </div>

            </div>


            <div class="timeline-item reveal">

                <div class="timeline-number">
                    02
                </div>


                <div>

                    <h3>
                        Somehow
                    </h3>

                    <p>

                        Conversations became memories,
                        and memories started becoming
                        something more.

                    </p>

                </div>

            </div>


            <div class="timeline-item reveal">

                <div class="timeline-number">
                    03
                </div>


                <div>

                    <h3>
                        Now
                    </h3>

                    <p>

                        There is a girl named Anuska,
                        a nickname called Lui,
                        and a story that matters.

                    </p>

                </div>

            </div>


            <div class="timeline-item reveal">

                <div class="timeline-number">
                    ∞
                </div>


                <div>

                    <h3>
                        Next
                    </h3>

                    <p>

                        More conversations.
                        More laughs.
                        More memories.

                        More chapters waiting to be written.

                    </p>

                </div>

            </div>

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 08 — PROMISE
===================================================== -->

<section class="promise">

    <div class="promise-box reveal">

        <div class="eyebrow">

            CHAPTER 08 · A PROMISE

        </div>


        <h3>

            SOME MEMORIES

            <span class="gold">
                ARE WORTH KEEPING.
            </span>

        </h3>


        <p>

            No matter how many birthdays pass,
            I hope there will always be new memories
            to look back on.

        </p>

    </div>

</section>


<!-- =====================================================
     CHAPTER 09 — SECRET
===================================================== -->

<section class="secret">

    <div class="secret-box reveal">

        <div class="secret-symbol">

            ✦

        </div>


        <div class="eyebrow">

            CHAPTER 09 · SECRET

        </div>


        <h2>

            THERE'S ONE MORE

            <span class="gold">
                THING.
            </span>

        </h2>


        <p>

            Some things are better revealed
            only when you are ready.

        </p>


        <button
            class="btn"
            id="unlockButton"
        >

            OPEN THE SECRET

        </button>


        <div id="secretMessage">

            Lui,

            if you ever wonder how much
            you mean to me...

            remember that I made
            an entire little universe
            just for you.

        </div>

    </div>

</section>


<!-- =====================================================
     CHAPTER 10 — FINAL LETTER
===================================================== -->

<section class="final-letter">

    <div class="container reveal">

        <div class="eyebrow">

            CHAPTER 10 · ONE LAST THING

        </div>


        <h2>

            IF WORDS

            <span class="gold">
                WERE ENOUGH...
            </span>

        </h2>


        <div class="final-message">

            I'd write a thousand pages.

            But I'd probably still end up
            saying the same thing:

            <br><br>

            <span>
                I'm really glad you're in my life.
            </span>

        </div>

    </div>

</section>


<!-- =====================================================
     FINAL SCENE
===================================================== -->

<section class="final">

    <div class="final-content reveal">

        <div class="eyebrow">

            THE END · OR MAYBE JUST THE BEGINNING

        </div>


        <h2>

            HAPPY

            <span class="gold">
                BIRTHDAY,
            </span>

            <br>

            LUI.

        </h2>


        <p>

            The music will eventually stop.

            The page will eventually end.

            The sparkles will keep flowing.

            But the reason this little universe
            exists will always remain.

        </p>


        <a
            href="#beginning"
            class="btn"
        >

            START AGAIN

        </a>


        <div class="final-name">

            Anuska · Lui

        </div>

    </div>

</section>


<!-- =====================================================
     FOOTER
===================================================== -->

<footer>

    <strong>
        FOR LUI
    </strong>


    <p>

        A little universe made especially for Anuska

    </p>

</footer>


<script>

/* =========================================================
   FLOWING SPARKLES
========================================================= */

const sparkleField =
    document.getElementById(
        "sparkleField"
    );


const sparkleCount =
    window.innerWidth < 600
        ? 120
        : 210;


for(
    let i = 0;
    i < sparkleCount;
    i++
){

    const sparkle =
        document.createElement(
            "span"
        );


    sparkle.className =
        "sparkle";


    const size =
        Math.random() * 3 + .5;


    sparkle.style.width =
        size + "px";


    sparkle.style.height =
        size + "px";


    sparkle.style.setProperty(
        "--startX",
        (Math.random() * 110 - 5)
        + "vw"
    );


    sparkle.style.setProperty(
        "--midX",
        (Math.random() * 110 - 5)
        + "vw"
    );


    sparkle.style.setProperty(
        "--endX",
        (Math.random() * 110 - 5)
        + "vw"
    );


    sparkle.style.setProperty(
        "--opacity",
        Math.random() * .75 + .20
    );


    sparkle.style.animationDuration =
        (Math.random() * 18 + 12)
        + "s";


    sparkle.style.animationDelay =
        (Math.random() * -30)
        + "s";


    sparkleField.appendChild(
        sparkle
    );

}


/* =========================================================
   BIRTHDAY COUNTDOWN
   LUI'S BIRTHDAY:
   5 OCTOBER 2026 — 12:00 AM IST
========================================================= */

const birthday =
    new Date(
        "2026-10-05T00:00:00+05:30"
    );


function updateCountdown(){

    const now =
        new Date();


    let difference =
        birthday - now;


    if(
        difference < 0
    ){

        difference = 0;

    }


    const days =
        Math.floor(
            difference /
            (
                1000 *
                60 *
                60 *
                24
            )
        );


    const hours =
        Math.floor(
            (
                difference /
                (
                    1000 *
                    60 *
                    60
                )
            ) % 24
        );


    const minutes =
        Math.floor(
            (
                difference /
                (
                    1000 *
                    60
                )
            ) % 60
        );


    const seconds =
        Math.floor(
            (
                difference /
                1000
            ) % 60
        );


    document
        .getElementById("days")
        .textContent =
        String(days)
        .padStart(2,"0");


    document
        .getElementById("hours")
        .textContent =
        String(hours)
        .padStart(2,"0");


    document
        .getElementById("minutes")
        .textContent =
        String(minutes)
        .padStart(2,"0");


    document
        .getElementById("seconds")
        .textContent =
        String(seconds)
        .padStart(2,"0");

}


updateCountdown();


setInterval(
    updateCountdown,
    1000
);


/* =========================================================
   SECRET UNLOCK
========================================================= */

const unlockButton =
    document.getElementById(
        "unlockButton"
    );


const secretMessage =
    document.getElementById(
        "secretMessage"
    );


unlockButton.addEventListener(
    "click",
    function(){

        secretMessage
            .classList
            .add("show");


        unlockButton.textContent =
            "SECRET OPENED";


        unlockButton.style.opacity =
            ".45";


        unlockButton.style.pointerEvents =
            "none";

    }
);


/* =========================================================
   SCROLL REVEAL
========================================================= */

const observer =
    new IntersectionObserver(

        entries => {

            entries.forEach(
                entry => {

                    if(
                        entry.isIntersecting
                    ){

                        entry.target
                            .classList
                            .add(
                                "visible"
                            );


                        observer.unobserve(
                            entry.target
                        );

                    }

                }
            );

        },

        {
            threshold:.10
        }

    );


document
    .querySelectorAll(
        ".reveal"
    )
    .forEach(
        element => {

            observer.observe(
                element
            );

        }
    );

</script>

</body>

</html>
