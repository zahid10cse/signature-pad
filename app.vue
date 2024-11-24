<template>
  <div>
    <NuxtRouteAnnouncer />

    <div style="display: grid; place-items: center; padding-top: 3rem">
      <div style="background: #d3d3d3; width: 450px; padding: 10px">
        <div style="background: white">
          <NuxtSignaturePad
            ref="signature"
            height="400px"
            width="400px"
            :max-width="options.maxWidth"
            :min-width="options.minWidth"
            :options="{
              penColor: options.penColor,
              backgroundColor: options.backgroundColor,
            }"
          />
        </div>
        <button type="button" @click="handleSave()">Save</button>
      </div>
    </div>
  </div>
</template>
<script setup>
const options = ref({
  penColor: 'rgb(0,0,0)',
  backgroundColor: 'rgb(255, 255, 255)',
  maxWidth: 2,
  minWidth: 2,
});
const signature = ref();

const handleSave = () => {
  var data = signature.value.saveSignature();
  console.log(data);
};
</script>
