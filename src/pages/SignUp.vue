<template>
  <div class="row">
    <div class="col-8">
      <q-page
        style="background: linear-gradient(to bottom, #238ffb 29%, #ffffff 100%);"
        class="flex flex-center"
      >
        <div class="q-pa-md">
       

          <q-stepper
            v-model="step"
            header-nav
            ref="stepper"
            color="primary"
            animated
          >
            <!-- <q-step
        :name="1"
        title="Select campaign settings"
        icon="settings"
        :done="step > 1"
        :header-nav="step > 1"
      >
        For each ad campaign that you create, you can control how much you're willing to
        spend on clicks and conversions, which networks and geographical locations you want
        your ads to show on, and more.

        <q-stepper-navigation>
          <q-btn @click="() => { done1 = true; step = 2 }" color="primary" label="Continue" />
        </q-stepper-navigation>
      </q-step> -->
            <q-step
              :name="1"
              title="Personal Information"
              icon="settings"
              :done="step > 1"
              :header-nav="step > 1"
            >
              <div class="row">
                <div class="col">
                  <div style="width:400px">
                    <q-input
                      dense
                      filled
                      v-model="fName"
                      label="First name *"
                      hint="Given Name"
                      lazy-rules
                      :rules="[
                        val =>
                          (val && val.length > 0) || 'Please type something'
                      ]"
                    />

                    <q-input
                      dense
                      filled
                      v-model="mName"
                      label="Middle name *"
                      hint="Middle name"
                      lazy-rules
                      :rules="[
                        val =>
                          (val && val.length > 0) || 'Please type something'
                      ]"
                    />

                    <q-input
                      dense
                      filled
                      v-model="lName"
                      label="Surname *"
                      hint="Surname"
                      lazy-rules
                      :rules="[
                        val =>
                          (val && val.length > 0) || 'Please type something'
                      ]"
                    />
                    <q-input
                      dense
                      filled
                      type="number"
                      v-model="age"
                      label="Your age *"
                      lazy-rules
                      :rules="[
                        val =>
                          (val !== null && val !== '') ||
                          'Please type your agee',

                        val =>
                          (val > 17 && val < 100) ||
                          'Please type a real age or you are under ag'
                      ]"
                    />
                    <q-input
                      dense
                      filled
                      v-model="pAddress"
                      label="Permanent Address *"
                      hint="Address"
                      lazy-rules
                      :rules="[
                        val =>
                          (val && val.length > 0) || 'Please type something'
                      ]"
                    />
                    <q-input
                      filled
                      dense
                      v-model="eAddress"
                      label="Email Address *"
                      hint="Electronic Mailing Address"
                      lazy-rules
                      :rules="[
                        val =>
                          (val && val.length > 0) || 'Please type something'
                      ]"
                    />
                    <q-input
                      filled
                      dense
                      v-model="number"
                      label="Contact Number*"
                      hint="Mobile Number"
                      lazy-rules
                      :rules="[
                        val =>
                          (val && val.length > 0) || 'Please type something'
                      ]"
                    />
                   <q-input
            color="blue-9"
            outlined
            v-model="password"
            filled
            :type="isPwd ? 'password' : 'text'"
            label="Password"
            standout="bg-white text-primary"
          >
          <template v-slot:append>
          <q-icon
            :name="isPwd ? 'visibility_off' : 'visibility'"
            class="cursor-pointer"
            @click="isPwd = !isPwd"
          />
          </template>
         </q-input>
                  </div>
                </div>
              </div>
              <div class="row"></div>

              <q-stepper-navigation>
                <q-btn
                  
                  color="primary"
                  label="Sign-up"
                  icon="forward"
                />
              </q-stepper-navigation>
            </q-step>
           

            <!-- <q-step
              :name="2"
              title="Skill set"
              caption="Optional"
              icon="engineering"
              :done="step > 2"
              :header-nav="step > 2"
            > -->
              <!-- <q-item>
                <q-item-section avatar>
                  <q-avatar
                    size="100x"
                    font-size="14px"
                    color="primary"
                    text-color="white"
                    icon="TouchApp"
                  />
                </q-item-section>

                <q-item-section>
                  <div class="q-gutter-sm text-h7 text-weight-bold ">
                    Select atleast 3 SKILL you possess
                  </div>
                </q-item-section>
              </q-item> -->

              <!-- <q-stepper-navigation>
                <q-btn
                  @click="
                    () => {
                      done2 = true;
                      step = 3;
                    }
                  "
                  color="primary"
                  label="Continue"
                />
                <q-btn
                  flat
                  @click="step = 1"
                  color="primary"
                  label="Back"
                  class="q-ml-sm"
                />
              </q-stepper-navigation>
            </q-step> -->

          </q-stepper>
        </div>
      </q-page>
    </div>

    <div class="col-4">
      <q-img src="~assets/bg.jpg" style="max-width: 800px; height: 600px;" />
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';

@Component({})
export default class PageIndex extends Vue {
  step = 1;
  fName = '';
  mName = '';
  lName = '';
  age = '';
  pAddress = '';
  eAddress = '';
  number = '';
  password = '';
   isPwd = true;
}

  //  addStudebt(): void {
  //  }

</script>

<style></style>
