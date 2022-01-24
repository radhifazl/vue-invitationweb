<template>
  <div class="journey-timeline container-fluid wood-bg">
      <div class="journey-timeline-wrapper wrapper-z-idx pt-5 mx-auto">
        <div class="journey-timeline-title font-title text-center">
            <h1>Our Love Journey</h1>
        </div>

        <div class="vertical-timeline mt-5" id="line">
            <div class="timeline">
                <ul class="timeline-list">
                    <li v-for="story in stories" :key="story.title" class="story-item mb-5">
                        <div class="tl-content p-2 px-3">
                            <h3 class="font-title">
                                {{ story.title }}
                            </h3>

                            <p class="desc font-sub">
                                {{ story.desc }}
                            </p>
                        </div>

                        <div class="tl-date mt-3">
                            <h3 class="font-title">
                                {{ story.date }}
                            </h3>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            stories: [
                {
                title: "Kenalan",
                date: "Mei 2017",
                desc: "Kisah ini berawal dari social media, N mengirimkan direct message kepada Q dengan bertanya - tanya perihal kegiatan sekolah"
                },
                {
                title: "Melamar",
                date: "Oktober 2021",
                desc: "Pada tanggal 17 Oktober 2021, N membawa keluarganya bersilaturahmi ke rumah Q dan merencanakan pernikahan bersama, beserta keluarga."
                },
                {
                title: "Akad Nikah",
                date: "Januari 2022",
                desc: "Setelah bersilaturahmi dan berdiskusi bersama dengan kedua keluarga, hingga diputuskanlah akad nikah pada hari Minggu, tanggal 9 Januari 2022."
                },
            ]
        }
    }
}
</script>

<style>
    .journey-timeline {
        height: 1000px;
    }

    .journey-timeline-wrapper {
        width: 90%;
    }

    .vertical-timeline {
        position: relative;
        height: 100%;
    }

    .vertical-timeline::after {
        content: '';
        position: absolute;
        top: 0;
        left: 3%;
        width: 4px;
        height: 100%;
        background: var(--second-fc);
    }

    .story-item {
        position: relative;
    }

    .tl-content:nth-child(odd):after {
        content: '';
        position: absolute;
        top: 10%;
        left: -5%;
        border-top: 20px solid transparent;
        border-bottom: 20px solid transparent;
        border-right: 50px solid #B3541E;
        z-index: -1;
    }

    .story-item::before {
        content: '';
        position: absolute;
        top: 14%;
        left: -12%;
        background: url("../assets/images/lovelist.svg");
        background-size: cover;
        background-position: center;
        width: 25px;
        height: 25px;
        z-index: 2;
    }

    .tl-content {
        background: var(--secondary-color);
        border-radius: 20px;
        position: relative;
    }

    @media screen and (min-width: 992px) {
        .journey-timeline {
            height: 900px;
        }

        .vertical-timeline::after {
            left: 50%;
        }

        .journey-timeline-wrapper {
            width: 85%;
        }

        .tl-content {
            width: 500px;
        }

        .story-item {
            display: flex;
            justify-content: space-between;
        }

        .story-item:nth-child(odd) {
            flex-direction: row-reverse;
        }

        .story-item::after {
            left: -4%;
        }

        .story-item:nth-child(even) .tl-content::after {
            content: '';
            position: absolute;
            top: 10%;
            left: 475px;
            border-top: 20px solid transparent;
            border-bottom: 20px solid transparent;
            border-right: none;
            border-left: 50px solid #B3541E;
            z-index: -1;
        }

        .story-item::before {
            left: 47.5%;
        }

        .tl-date {
            position: absolute;
        }

        .story-item:nth-child(odd) .tl-date {
            left: 30%;
        }

        .story-item:nth-child(even) .tl-date {
            right: 33%;
        }
    }
</style>