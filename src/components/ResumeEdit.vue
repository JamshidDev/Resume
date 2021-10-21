<template>
  <div>

  
  <div v-if="editShow" class="container">
    <div class="row">
      <div class="col-sm-12">
        <p class="text-center resume-title">МАЪЛУМОТНОМА</p>
      </div>
      <div class="col-sm-8 resume-container">
        <div class="box-input-resume mb-3">
          <input
            type="text"
            class="form-control input-fullNAme"
            v-model="resume.fullName"
          />
        </div>
        <div class="box-input-resume d-flex align-items-center">
          <input
            type="text"
            class="form-control rw mr-1"
            v-model="resume.currentYear"
          />
          йил
          <input
            type="text"
            class="form-control rw ml-1"
            v-model="resume.currentMonth"
          />
          :
        </div>
        <p class="text-left font-bold6">
          Ўзбекистон Республикаси Ахборот технологиялари ва коммуникацияларини
          ривожлантириш вазирлиги Ташкилий назорат бошқармаси Раҳбарият котиби
        </p>
      </div>
      <div class="col-sm-4">
        <img src="../assets/resume.jpg" class="img-thumbnail" alt="Not found" />
      </div>
      <div class="col-sm-12 d-flex mb-3">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Туғилган йили:</p>
          <input
            type="text"
            class="form-control rw"
            v-model="resume.bornYear"
          />
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Туғилган жойи:</p>
          <input
            type="text"
            class="form-control rw"
            v-model="resume.bornLive"
          />
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Миллати:</p>
          <input type="text" class="form-control rw" v-model="resume.nation" />
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Партиявийлиги:</p>
          <input type="text" class="form-control rw" v-model="resume.party" />
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Маълумоти:</p>
          <input type="text" class="form-control rw" v-model="resume.degree" />
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Тамомлаган:</p>
          <input
            type="text"
            class="form-control rw"
            v-model="resume.endDegree"
          />
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <p class="text-left font-bold6 m-0 w-50">
          Маълумоти бўйича мутахассислиги:
        </p>
        <input
          type="text"
          class="form-control rw w-50"
          v-model="resume.specialty"
        />
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Илмий даражаси:</p>
          <input
            type="text"
            class="form-control rw"
            v-model="resume.academicDegree"
          />
        </div>
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Илмий унвони:</p>
          <input
            type="text"
            class="form-control rw"
            v-model="resume.academicTitle"
          />
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 rw m-0">Қайси чет тилларини билади:</p>
          <input
            type="text"
            class="form-control rw"
            v-model="resume.knewForeign"
          />
        </div>
      </div>
      <div class="col-sm-12 d-flex mb-2">
        <div class="box-info-resume">
          <p class="text-left font-bold6 w-100 m-0">
            Давлат мукофотлари билан тақдирланганми (қанақа):
          </p>
          <input type="text" class="form-control rw" v-model="resume.awards" />
        </div>
      </div>

      <div class="col-sm-12 d-flex mb-2">
        <div>
          <p class="text-left font-bold6 w-100 m-0">
            Халқ депутатлари республика, вилоят, шаҳар ва туман Кенгаши
            депутатими ёки бошқа сайланадиган органларнинг аъзосими (тўлиқ
            кўрсатилиши лозим):
          </p>
          <input type="text" class="form-control rw" v-model="resume.member" />
        </div>
      </div>
      <div class="col-sm-12">
        <p class="text-center resume-title">МЕҲНАТ ФАОЛИЯТИ</p>
      </div>
      <div class="col-sm-12 mb-4">
        <div class="box-add-info-container">
          <input
            type="text"
            class="form-control"
            style="height: 30px"
            v-model="resume.mehnatInfo"
          />
          <button
            @click="handlerMehnatInfo"
            class="btn btn-primary btn-add-info"
          >
            +
          </button>
        </div>
      </div>

      <div class="col-sm-12 mb-5">
        <p
          class="text-left font-bold6 mb-2"
          v-for="item in resume.infoArrey"
          :key="item"
        >
          {{ item }}
        </p>
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
          <input
            type="text"
            class="form-control rw"
            v-model="resume.fullName"
          />нинг яқин қариндошлари ҳақида
        </div>
        <p class="text-center resume-title w-100">МАЪЛУМОТ</p>
        <!-- Button trigger modal -->
        <button
          type="button "
          class="btn btn-add-info btn-secondary"
          data-bs-toggle="modal"
          data-bs-target="#exampleModal"
        >
          Adding
        </button>
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
            <tr>
              <th scope="row">Отаси</th>
              <td>Расулов Абдулатиф Абдухалилович</td>
              <td>1946 йил, Тошкент шаҳри</td>
              <td>Пенсияда («Безаш рассомчилик» корхонаси ходими)</td>
              <td>Тошкент шаҳри, Шайҳонтохур тумани, Ибн Сино кўчаси, 21-уй</td>
            </tr>
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
      <div class="col-sm-12">
        <!-- Modal -->
        <div
          class="modal fade"
          id="exampleModal"
          tabindex="-1"
          aria-labelledby="exampleModalLabel"
          aria-hidden="true"
        >
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title" id="exampleModalLabel">Add new Info</h5>
                <button
                  type="button"
                  class="btn-close"
                  data-bs-dismiss="modal"
                  aria-label="Close"
                ></button>
              </div>
              <div class="modal-body">
                <div class="mb-3">
                  <label
                    for="exampleInputEmail1"
                    class="form-label moda-title-resume"
                    >Қарин-дошлиги</label
                  >
                  <input
                    type="email"
                    class="form-control"
                    v-model="resume.relatives.rateRelative"
                  />
                </div>
                <div class="mb-3">
                  <label
                    for="exampleInputEmail1"
                    class="form-label moda-title-resume"
                    >Фамилияси, исми ва отасининг исми
                  </label>
                  <input
                    type="email"
                    class="form-control"
                    v-model="resume.relatives.fullName"
                  />
                </div>
                <div class="mb-3">
                  <label
                    for="exampleInputEmail1"
                    class="form-label moda-title-resume"
                    >Туғилган йили ва жойи
                  </label>
                  <input
                    type="email"
                    class="form-control"
                    v-model="resume.relatives.bornYear"
                  />
                </div>
                <div class="mb-3">
                  <label
                    for="exampleInputEmail1"
                    class="form-label moda-title-resume"
                    >Иш жойи ва лавозими
                  </label>
                  <input
                    type="email"
                    class="form-control"
                    v-model="resume.relatives.jobPlace"
                  />
                </div>
                <div class="mb-3">
                  <label
                    for="exampleInputEmail1"
                    class="form-label moda-title-resume"
                    >Турар жойи</label
                  >
                  <input
                    type="email"
                    class="form-control"
                    v-model="resume.relatives.livePlace"
                  />
                </div>
              </div>
              <div class="modal-footer">
                <button
                  type="button"
                  class="btn btn-secondary btn-add-info"
                  data-bs-dismiss="modal"
                >
                  Close
                </button>
                <button
                  type="button "
                  class="btn btn-primary btn-add-info"
                  data-bs-dismiss="modal"
                  @click="handlerRelative"
                >
                  Save changes
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-sm-12">
        <button type="button" @click="logger" class="btn btn-secondary btn-add-info">Generate resume</button>
      </div>
    </div>
  </div>
  <!-- Generate page -->
  <GeneratePage v-if="isShow"  :resume="resume" />

  </div>
</template>

<script>
import GeneratePage from "./GeneratePage.vue"
export default {
  name: "ResumeEdit",
  components:{
    GeneratePage,
  },
  data() {
    return {
      resume: {
        fullName: "",
        currentYear: "",
        currentMonth: "",
        bornYear: "",
        bornLive: "",
        nation: "",
        party: "",
        degree: "",
        endDegree: "",
        specialty: "",
        academicDegree: "",
        academicTitle: "",
        knewForeign: "",
        awards: "",
        member: "",
        mehnatInfo: "",
        relatives: {
          rateRelative: "",
          fullName: "",
          bornYear: "",
          jobPlace: "",
          livePlace: ""  },
          infoArrey: [],
        relativeArrey: [],
      },
      isShow:false,
      editShow:true,
    };
  },
  methods: {
    handlerMehnatInfo() {
      this.resume.infoArrey.push(this.resume.mehnatInfo);
      console.log(this.resume.infoArrey);
    },
    handlerRelative() {
      this.resume.relativeArrey.push(this.resume.relatives);
      console.log(this.resume.relativeArrey);
    },
    logger(){
      this.isShow=true;
      this.editShow=false;
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
  padding: 0px 200px;
  margin-bottom: 200px;
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
  font-weight: 700;
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
