<template>
  <div class="vertical-timeline container-fluid wood-bg">
    <div class="vertical-timeline-wrapper wrapper-z-idx">
      <div class="timeline-title font-title text-center">
        <h1>Our Love Journey</h1>
      </div>

      <div class="timeline">
        <ul class="timeline-list">
          <li v-for="story in stories" :key="story.title" class="mb-5">
            <div class="tl-content py-2 px-3">
              <h3 class="font-title">{{ story.title }}</h3>
              <p class="desc font-sub">
                {{ story.desc }}
              </p>
            </div>

            <div class="tl-time">
              <h5 class="font-title">{{ story.date }}</h5>
            </div>
          </li>
          <div style="clear: both"></div>
        </ul>
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
  .vertical-timeline {
    height: 1000px;
  }

  .timeline {
    position: relative;
  }

  .timeline::before {
      content: '';
      position: absolute;
      left: 50%;
      width: 3px;
      height: 100%;
      background: #67481A;
  } 

  .timeline-list li {
    position: relative;
    width: 60%;
  }

  .timeline-list li:nth-child(even) {
      float: left;
      clear: both;
      transform: translateX(-16rem);
  }

  .timeline-list li:nth-child(odd) {
      float: right;
      clear: both;
  }

  .tl-content {
      width: 400px;
      background: var(--secondary-color);
      position: relative;
      margin: 0 5rem;
  }

  .tl-content::after {
      content: '';
      position: absolute;
      width: 0;
      height: 0;
      border-top: 30px solid transparent;
      border-bottom: 30px solid transparent;
      border-left: 50px solid var(--secondary-color);
      top: 20px;
      right: -8%;
      z-index: -1;
  }

  .timeline-list li:nth-child(odd) .tl-content::after {
      left: -8%;
      border-right: 50px solid var(--secondary-color);
      border-left: none;
  }

  .timeline-list .tl-time {
      position: absolute;
      top: 15%;
      padding: 8px 16px;
  }

  .timeline-list .tl-time h5 {
      color: var(--white-fc);
  }

  .timeline-list li:nth-child(even) .tl-time {
      right: -100%;
  }

  .timeline-list li:nth-child(odd) .tl-time {
      left: -40%;
  }

  @media screen and (max-width: 992px) {
      .timeline::before {
          left: -5%;
      }

      .tl-content {
          width: 100% !important;
      }

      .tl-content h3 {
        font-size: 1.2rem;
      }

      .tl-content::after {
        left: -8%;
        border-right: 50px solid var(--secondary-color);
        border-left: none;
      }


      .timeline-list li {
        width: 100%;
      }


      .timeline-list li:nth-child(odd) {
          float: none;
          clear: none;
      }
      
      .timeline-list li:nth-child(even) {
          float: none;
          clear: none;
          transform: translateX(0);
      }
      
      .timeline-list .tl-time {
          position: static;
          padding: 0;
          margin-top: 5rem;
      }
  }
</style>