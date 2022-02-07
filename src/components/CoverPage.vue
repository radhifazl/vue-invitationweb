<template>
  <div class="cover-page container-fluid text-center" id="cover">
      <div class="cover-page-content">
        <div class="cover-couple mt-3 p-3">
            <div class="couple-img mx-auto">
                <img src="../assets/images/coverpage/couplecover.svg" alt="Couple" id="cover-couple">

                <img src="../assets/images/coverpage/coverleafl.svg" alt="Leaf" id="leaf-left">
                <img src="../assets/images/coverpage/coverleafr.svg" alt="Leaf" id="leaf-right">
            </div>
        </div>

        <div class="covercouple-text">
            <h1 class="font-title">Qeza & Novan</h1>

            <h5 class="font-title m-3 m-lg-4">Kepada bpk/ibu/saudara/i</h5>

            <h4 class="font-sub" style="font-weight: 600">Keluarga Besar</h4>

            <h5 class="font-title m-3 m-lg-4">
                Tanpa mengurangi rasa hormat, kami mengundang anda untuk hadir di acara pernikahan kami
            </h5>

            <div class="cover-button mt-3 mt-lg-4">
                <button class="open-btn" @click="openInvitation">Buka Undangan</button>
            </div>
        </div>
      </div>
  </div>
</template>

<script>

export default {
    methods: {
        openInvitation() {
            const cover = document.getElementById('cover'),
                  home = document.getElementById('home'),
                  couple = document.getElementById('couple'),
                  event = document.getElementById('event'),
                  gallery = document.getElementById('gallery'),
                  wishes = document.getElementById('wishes');
            
            const arrComp = [home, couple, event, gallery, wishes]; // Array of Components

            arrComp.forEach(comp => {
                comp.style.display = "block";
                cover.classList.add("closed");
            })
        }
    }
}
</script>

<style>
    .cover-page {
        height: 100vh;
        position: fixed;
        top: 0;
        left: 0;
        z-index: 1100;
        background: url("../assets/images/coverpage/coverwood-bg.png");
        background-size: cover;
        background-position: center;
        display: grid;
        place-items: center;
        transition: 0.35s ease;
    }

    .cover-page.closed {
        animation: skewed 1.5s ease;
        animation-fill-mode: forwards;
    }

    @keyframes skewed {
        0% {
            opacity: 1;
            transform: translateY(0);
        }

        50% {
            transform: translateY(-20rem);
        }

        100% {
            transform: translateY(-80rem);
            opacity: 0;
            visibility: hidden;
            user-select: none;
        }
    }

    @keyframes scaled {
        from {
            transform: scale(0);
        }
        to {
            transform: scale(10);
            opacity: 0;
            visibility: hidden;
            user-select: none;
        }
    }

    .couple-img {
        position: relative;
        width: 200px;
        border-radius: 50%;
        border: 5px solid #ffffff;
    }

    .couple-img #cover-couple {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .couple-img > #leaf-left, #leaf-right {
        position: absolute;
        bottom: 0;
        max-width: 120px;
    }

    .couple-img > #leaf-left {
        left: -30%;
    }

    .couple-img > #leaf-right {
        right: -30%;
    }

    .covercouple-text h1 {
        font-size: 3rem;
    }

    .covercouple-text h5 {
        color: #ffffff;
    }
    .open-btn {
        background: #B3541E;
        border-radius: 10px;
        border: none;
        outline: none;
        padding: 0.4rem 2.2rem;
        font-family: var(--first-font);
        cursor: pointer;
        transition: all 0.3s ease;
    }

    .open-btn:hover {
        background: #be581d;
        border-radius: 0;
        transform: translateY(-0.3rem);
    }

    @media screen and (min-width: 992px) {
        .open-btn {
            font-size: 1.3rem;
        }
    }
</style>