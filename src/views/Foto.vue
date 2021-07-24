<template>
  <div class="wrapper">
    <parallax
      class="section page-header header-filter"
      :style="headerStyle"
    ></parallax>
    <div class="main main-raised">
      <div class="section profile-content">
        <div class="container">
          <div class="md-layout">
            <div class="md-layout-item md-size-100 mx-auto">
              <div class="profile">
                <div class="avatar">
                  <img
                    :src="img"
                    alt="Circle Image"
                    class="img-raised rounded-circle img-fluid"
                  />
                </div>
                <div class="name">
                  <h3 class="title">Reconozcamos tu estado</h3>
                  <h5>Tomaremos una foto tuya para saber cómo estás.</h5>
                </div>
                <div class="md-layout">
                  <div class="md-layout-item md-size-100">
                    <md-datepicker v-model="selectedDate">
                      <label>Seleccionar día</label>
                    </md-datepicker>
                  </div>
                </div>
                <md-field>
                  <md-textarea v-model="initial" placeholder="Escribe aquí..."></md-textarea>
                </md-field>
              </div>
            </div>
          </div>
          <div class="profile-tabs">

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Tabs } from "@/components";
export default {
  components: {
  },
  bodyClass: "profile-page",
  data() {

  },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/city-profile.jpg")
    },
    img: {
      type: String,
      default: require("@/assets/img/icons/diario.png")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="scss" scoped>
.section {
  padding: 0;
}

.profile-tabs::v-deep {
  .md-card-tabs .md-list {
    justify-content: center;
  }

  [class*="tab-pane-"] {
    margin-top: 3.213rem;
    padding-bottom: 50px;

    img {
      margin-bottom: 2.142rem;
    }
  }
}
</style>
