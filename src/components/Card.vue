<template>
  <q-card :style="$q.screen.lt.md ? 'width: 100%' : 'width: 25%'">


















































































































    <!-- <q-img
      :src="require(`../assets/${jobPhoto}`)"
      @mouseenter="showReport = true"
      @mouseleave="showReport = false"
    >
      <div
        v-if="showReport"
        class="bg-transparent text-subtitle2 absolute-top text-right"
      >
        <q-btn
          round
          color="red"
          icon="info"
          @click.prevent.stop="showReportButton = true"
        />
      </div>
    </q-img> -->

    <q-card-section avatar>
      <q-btn
        round
        class="absolute"
        style="top: 0; right: 12px; transform: translateY(-50%)"
        :to="to"
      >
        <q-avatar size="70px">
          <!-- <img :src="require(`../assets/${profilePic}`)" /> -->
        </q-avatar>
      </q-btn>

      <div class="row no-wrap items-center">
        <div class="col text-h6 ellipsis">{{ job }}</div>
        <div
          class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
        >
          <q-icon name="person" />
          Employer
        </div>
      </div>
      <div class="text-caption text-grey">
        <q-icon name="location_on" />
       {{ location }}
      </div>
    </q-card-section>

    <q-card-section class="q-pt-none">
      <div class="text-subtitle1">₱・{{ salary }}</div>
      <div class="text-body2 text-grey-9">
        {{ jobdesc }}
      </div>
    </q-card-section>

    <q-separator />

    <q-card-actions align="center">
      <!-- <q-btn color="light-blue-10" icon="send" label="Send Application" /> -->
      <q-btn
        label="Send Application"
        color="primary"
        icon="send"
        @click="alerts = true"
      />

      <q-dialog v-model="alerts" persistent>
        <q-card>
          <q-card-section class="row items-center">
            <q-avatar icon="thumb_up_alt" color="primary" text-color="white" />
            <span class="q-ml-sm">Send Application?.</span>
          </q-card-section>

          <q-card-actions align="right">
            <q-btn
              flat
              @click="Confirm = true"
              label="Confirm"
              color="primary"
              v-close-popup
            />

            <q-btn flat label="Cancel" color="primary" v-close-popup />
          </q-card-actions>
        </q-card>
      </q-dialog>

      <q-dialog v-model="showReportButton">
        <q-card>
          <q-toolbar>
            <q-avatar>
              <img src="" />
            </q-avatar>

            <q-toolbar-title
              ><span class="text-weight-bold">Report</span>
              Reason</q-toolbar-title
            >

            <q-btn flat round dense icon="close" v-close-popup />
          </q-toolbar>

          <q-card-section class="q-pt-none">
            <div class="q-pa-md">
              <div class="q-gutter-sm">
                <q-radio v-model="shape" val="line" label="Line" />
                <q-radio v-model="shape" val="rectangle" label="Rectangle" />
                <q-radio v-model="shape" val="ellipse" label="Ellipse" />
                <q-radio v-model="shape" val="polygon" label="Polygon" />
              </div>

              <div class="q-px-sm">
                Your selection is: <strong>{{ shape }}</strong>
              </div>
            </div>
          </q-card-section>

          <q-card-actions align="right">
            <q-btn flat label="OK" color="primary" v-close-popup />
          </q-card-actions>
        </q-card>
      </q-dialog>
    </q-card-actions>
  </q-card>
</template>

<script>
export default {
  name: 'Card',
  props: ['jobPhoto', 'profilePic', 'job', 'stars', 'salary', 'jobdesc', 'location','to'],
  data() {
    return {
      alerts: false,
      confirm: false,
      showReport: false,
      showReportButton: false,
      confirmReport: false,
      shape: 'line'
    };
  }
};
</script>

<style scoped>
.q-img {
  height: 200px;
}

.q-card__section {
  height: 100px;
}
</style>
