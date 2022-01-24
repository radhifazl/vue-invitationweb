<template>
  <div class="first-section container-fluid text-center py-5 wood-bg">
        <img src="../assets/images/pinkflower1.svg" alt="Pink Flower" id="pf-1">
        <img src="../assets/images/pinkflower2.svg" alt="Pink Flower" id="pf-2">
    <div class="first-section-content"> 
        <div class="bride-initial m-auto pt-5">
            <img src="../assets/images/pinkflower-shield3.svg" alt="Pink Flower" id="pfs-1">
            <img src="../assets/images/pinkflower-shield4.svg" alt="Pink Flower" id="pfs-2">
            <div class="shield">
                <img src="../assets/images/shield.svg" alt="Shield">
                <div class="initial-name font-title">
                    <h1 class="men-initial">Q</h1>
                    <div class="border my-1"></div>
                    <h1 class="women-initial">N</h1>
                </div>
            </div>
        </div>
        <div class="bride-name mt-3 py-3">
            <h1 class="font-title">Qeza & Novan</h1>
        </div>
        <div class="invite-text font-sub">
            <p>We Invited You To Celebrate Our Wedding <br> Minggu, 09 Januari 2022</p>
        </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    .first-section {
        min-height: 100vh;
        position: relative;
    }

    .first-section::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 20%;
        background: linear-gradient(0deg, #a35632d0 30%, transparent);
    }

    .first-section-content {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 100;
    }

    .first-section #pf-1, #pf-2 {
        position: absolute;
        top: 0;
        max-width: 200px;
        z-index: 1000;
    }

    .first-section #pf-1 {
        left: 0;
    }

    .first-section #pf-2 {
        right: 0;
    }

    .bride-initial {
        width: 150px;
        position: relative;
    }

    .bride-initial #pfs-1, #pfs-2 {
        position: absolute;
        bottom: -10%;
        max-width: 200px;
    }

    .bride-initial #pfs-1 {
        left: -40%;
    }

    .bride-initial #pfs-2 {
        right: -40%;
    }

    .shield {
        position: relative;
    }

    .shield img {
        max-width: 150px;
    }

    .shield .initial-name {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .initial-name h1 {
        color: var(--white-fc);
    }

    .border {
        width: 100%;
        background: var(--white-fc);
        height: 2px;
    }

    .bride-name h1 {
        color: var(--white-fc);
        font-size: 3rem;
    }

    .invite-text {
        width: 300px;
        font-weight: 600;
    }

    /* === Desktop Ver === */
    @media screen and (min-width: 992px) {
        .first-section #pf-1, #pf-2 {
            max-width: 400px;
        }

        .bride-initial {
            width: 300px;
        }

        .bride-initial #pfs-1, #pfs-2 {
            max-width: 300px;
        }

        .bride-initial #pfs-1 {
            left: -20%;
        }

        .bride-initial #pfs-2 {
            right: -20%;
        }

        .shield img {
            max-width: 250px;
        }

        .initial-name h1 {
            font-size: 4rem;
        }

        .invite-text {
            padding-bottom: 5rem;
        }
    }
</style>