<script setup>
import { store } from "../js/state";
import HoverCard from "../components/HoverCard.vue";

const emit = defineEmits(["onClick"]);

// Set firmware and targetType in state store, then update page to pages selection page
function setFirmware(firmware, targetType) {
  store.firmware = firmware;
  store.targetType = targetType;
  emit("onClick");
}
</script>

<template>
  <div class="section">
    <div class="containerMain">
      <div class="containerHeader">
        <VCardTitle>Main RC Firmware</VCardTitle>
        <VCardSubtitle
          >Controlled or controlling... we got you covered!</VCardSubtitle
        >
      </div>
      <VRow>
        <VCol md="6">
          <HoverCard
            min-height="100%"
            @click="setFirmware('firmware', 'tx')"
            image="Transmitter.png"
            title="Transmitter"
            text="Flash your external transmitter module, JR Bay (Micro) or Nano module; or an internal module
                 built into your radio handset."
          />
        </VCol>
        <VCol md="6">
          <HoverCard
            min-height="100%"
            @click="setFirmware('firmware', 'rx')"
            image="Receiver.png"
            title="Receiver"
            text="Serial connected and PWM receivers alike may flashed here."
          />
        </VCol>
      </VRow>
    </div>
    <div class="containerMain">
      <div class="containerHeader">
        <VCardTitle>Backpack Firmware</VCardTitle>
        <VCardSubtitle>Wireless control of all the things!</VCardSubtitle>
      </div>
      <VRow>
        <VCol md="6">
          <HoverCard
            min-height="100%"
            @click="setFirmware('backpack', 'txbp')"
            image="Transmitter_Module.png"
            title="Transmitter Module"
            text="Built in to most transmitters, it communicates with the other backpacks or via WiFi to a computer
                 running Mission Planner (or other) for MAVLink craft."
          />
        </VCol>
        <VCol md="6">
          <HoverCard
            min-height="100%"
            @click="setFirmware('backpack', 'vrx')"
            image="Video_Receiver.png"
            title="Video Receiver"
            text="A built-in VRx backpack like the HDZero goggles backpack, or the SkyZone ELRS backpack; or a
                 DIY solution connected to a VRx allows you to always have your goggles on the right channel."
          />
        </VCol>
      </VRow>
      <VRow>
        <VCol md="6">
          <HoverCard
            min-height="100%"
            @click="setFirmware('backpack', 'aat')"
            image="Antenna_Tracker.png"
            title="Antenna Tracker"
            text="Flying long-range and need your antenna pointed in just the right direction? This is the backpack
                 for you!"
          />
        </VCol>
        <VCol md="6">
          <HoverCard
            min-height="100%"
            @click="setFirmware('backpack', 'timer')"
            image="Race_Timer.png"
            title="Race Timer"
            text="Connects to the RotorHazard race timing system and sends OSD message with lap times and current
                 place during the race so you always know where you're placed."
          />
        </VCol>
      </VRow>
    </div>
  </div>
</template>

<style scoped>
.containerMain {
  z-index: 9999;
  background-color: #fff;
  padding: 40px;
  border-radius: 0.75rem;
  box-shadow: 0px 4px 16px 0px rgba(0, 0, 0, 0.16);
}

.containerHeader {
  margin-bottom: 40px;
}

.v-card-title {
  padding: 0;
  font-size: 1.5rem;
  font-weight: 600;
  color: #242527;
}

.v-card-subtitle {
  padding: 0;
  font-size: 1rem;
  color: #242527;
}

.section {
  margin-top: -80px;
  display: flex;
  flex-direction: column;
  gap: 40px;
  text-align: center;
}

@media (max-width: 640px) {
  .containerMain{
    padding: 20px;
  }
  .section{
    margin-top: -60px;
  }
}
</style>
