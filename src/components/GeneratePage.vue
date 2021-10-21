<template>
  <div class="container border" style="padding:50px;">
    <div class="row">
      <div class="col-sm-12">
        <p class="text-center resume-title">МАЪЛУМОТНОМА</p>
        <p class="resume-title text-center">{{ resume.fullName }}</p>
      </div>
      <div class="col-sm-8 resume-container">
        <div class="box-input-resume text-left">
          {{ resume.currentYear }}йил
          {{ resume.currentMonth }}
          :
        </div>
        <p class="text-left font-bold6">
          Ўзбекистон Республикаси Ахборот технологиялари ва коммуникацияларини
          ривожлантириш вазирлиги Ташкилий назорат бошқармаси Раҳбарият котиби
        </p>
        <div class="d-flex">
             <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Туғилган йили:</p>
          <p class="text-left m-0">{{ resume.bornYear }}</p>
        </div>
        <div class="box-info-resume" style="padding-left:170px">
          <p class="text-left font-bold6 rw m-0">Туғилган жойи:</p>
          <p class="text-left m-0">{{ resume.bornLive }}</p>
        </div>
        </div>
      </div>
      <div class="col-sm-4">
        <img src="../assets/resume.jpg" class="img-thumbnail" alt="Not found" />
      </div>
      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Миллати:</p>
          <p class="text-left m-0">{{ resume.nation }}</p>
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Партиявийлиги:</p>
          <p class="text-left m-0">{{ resume.party }}</p>
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Маълумоти:</p>
          <p class="text-left m-0">{{ resume.degree }}</p>
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Тамомлаган:</p>
          <p class="text-left m-0">{{ resume.endDegree }}</p>
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <p class="text-left font-bold6 m-0 w-50">
          Маълумоти бўйича мутахассислиги:
        </p>
        <p class="text-left m-0 w-50">{{ resume.specialty }}</p>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Илмий даражаси:</p>
          <p class="text-left m-0">{{ resume.academicDegree }}</p>
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Илмий унвони:</p>
          <p class="text-left m-0">{{ resume.academicTitle }}</p>
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Қайси чет тилларини билади:</p>
          <p class="text-left m-0">{{ resume.knewForeign }}</p>
        </div>
      </div>
      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 w-100 m-0">
            Давлат мукофотлари билан тақдирланганми (қанақа):
          </p>
          <p class="text-left m-0">{{ resume.awards }}</p>
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div>
          <p class="text-left font-bold6 w-100 m-0">
            Халқ депутатлари республика, вилоят, шаҳар ва туман Кенгаши
            депутатими ёки бошқа сайланадиган органларнинг аъзосими (тўлиқ
            кўрсатилиши лозим):
          </p>
          <p class="text-left m-0">{{ resume.member }}</p>
        </div>
      </div>
      <div class="col-sm-12">
        <p class="text-center resume-title">МЕҲНАТ ФАОЛИЯТИ</p>
      </div>
      <div class="col-sm-12 mb-3">
        <p
          class="text-left font-bold6 mb-2"
          v-for="item in resume.infoArrey"
          :key="item"
        >
          {{ item }}
        </p>
      </div>

      <div class="col-sm-12 mb-5">
        <p class="text-left font-bold6 mb-2"></p>
      </div>

      <div class="col-sm-12 mb-2 resume-container">
        <div
          class="
            box-input-resume
            d-flex
            align-items-center
            justify-content-center
            mb-2
          "
          style="font-size: 14px; font-weight: 600"
        >
          {{ resume.fullName }}нинг яқин қариндошлари
          ҳақида
        </div>
        <p class="text-center resume-title w-100">МАЪЛУМОТ</p>
        <!-- Button trigger modal -->
      </div>
      <div class="col-sm-12">
        <table class="table border-striped">
          <thead>
            <tr>
              <th scope="col">Қарин-дошлиги</th>
              <th scope="col">Фамилияси, исми ва отасининг исми</th>
              <th scope="col">Туғилган йили ва жойи</th>
              <th scope="col">Иш жойи ва лавозими</th>
              <th scope="col">Турар жойи</th>
            </tr>
            
          </thead>
          <tbody>
            <tr v-for="item in resume.relativeArrey" :key="item.livePlace">
              <th scope="row">{{ item.rateRelative }}</th>
              <td>{{ item.fullName }}</td>
              <td>{{ item.bornYear }}</td>
              <td>{{ item.jobPlace }}</td>
              <td>{{ item.livePlace }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GeneratePage",
  props: {
    resume: Object,
  },
};
</script>

<style  scoped>
* {
  font-family: "times-new-roman";
  font-size: 11px;
}
input {
  height: 20px;
  font-size: 12px;
}
.btn-add-info {
  padding: 4px 12px;
  height: 30px;
}
.container {
  padding: 0px 50px;
}
@font-face {
  font-family: "times-new-roman";
  src: url("../assets/fonts/times-new-roman-cyr.ttf");
}
.resume-container {
  display: flex;
  flex-direction: column;
}
.resume-title {
  font-family: "times-new-roman";
  font-size: 14px;
  font-weight: 600;
}
.input-fullNAme {
  width: 50%;
  margin: 0px 25%;
}
.rw {
  width: 200px;
}

.img-thumbnail {
  width: 100px;
}
.font-bold6 {
  font-weight: 900;
}
.box-info-resume {
  width: 50%;
}
.box-add-info-container {
  display: flex;
}
.moda-title-resume {
  text-align: left !important;
  width: 100%;
}
</style>