<template>
  <b-container>
    <b-row>
      <b-col sm="6" offset-sm="3">
        <b-card class="mt-4">
          <b-row class="justify-content-between mx-2">
            <label for="volume">Volume</label>
            <b-form-input
              id="volume"
              v-model="volume"
              type="range"
              min="0"
              max="10"
            />
          </b-row>
          <b-row class="mx-2 mt-2"
            ><b-button disabled size="sm" class="mb-2">
              <b-icon icon="gear-fill" aria-hidden="true"></b-icon> Settings
            </b-button></b-row
          >
        </b-card>
        <b-card class="mt-4">
          <b-row>
            <b-col
              ><DrumPart
                name="Crash Cymbal"
                fileName="Cymbal16iCrash-1.wav"
                :volume="volume"
                keyBind="KeyQ"
            /></b-col>
            <b-col
              ><DrumPart
                name="High Tom"
                fileName="HiTom-1.wav"
                :volume="volume"
                keyBind="KeyW"
            /></b-col>
            <b-col
              ><DrumPart
                name="Medium Tom"
                fileName="MidTom-1.wav"
                :volume="volume"
                keyBind="KeyE"
            /></b-col>
            <b-col
              ><DrumPart
                name="Ride Cymbal"
                fileName="Cymbal16iRide-HV1.wav"
                :volume="volume"
                keyBind="KeyR"
            /></b-col>
          </b-row>
          <b-row>
            <b-col
              ><DrumPart
                name="Hi Hat"
                fileName="ClosedHiHat-1.wav"
                :volume="volume"
                keyBind="KeyA"
            /></b-col>
          </b-row>
          <b-row>
            <b-col
              ><DrumPart
                name="Snare Drum"
                fileName="SnareDrum1-HV1.wav"
                :volume="volume"
                keyBind="KeyS"
            /></b-col>
            <b-col sm="6"
              ><DrumPart
                name="Bass Drum"
                fileName="BassDrum-HV1.wav"
                :volume="volume"
                keyBind="Space"
            /></b-col>
            <b-col
              ><DrumPart
                name="Floor Tom"
                fileName="LowTom-1.wav"
                :volume="volume"
                keyBind="KeyC"
            /></b-col>
          </b-row>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import DrumPart from "./DrumPart.vue";

export default {
  components: { DrumPart },
  data() {
    return {
      volume: "5",
    };
  },
};
</script>

<style></style>
