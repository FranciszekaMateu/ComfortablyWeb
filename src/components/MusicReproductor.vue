<script>
import { Howl } from 'howler';
import { storage } from '../services/firebaseConfig.js'; // Asegúrate de que la ruta sea correcta
import { ref, getDownloadURL } from 'firebase/storage';

export default {
  data() {
    return {
      sound: null,
    };
  },
  methods: {
    loadAudio() {
      const audioRef = ref(storage, '(03) Time.flac'); // Asegúrate de que la ruta sea correcta

      getDownloadURL(audioRef)
        .then((url) => {
          this.sound = new Howl({
            src: [url],
            format: ['flac']
          });
        })
        .catch((error) => {
          console.error('Error fetching audio:', error);
        });
    },
    playAudio() {
      if (this.sound) {
        this.sound.play();
      }
    },
    pauseAudio() {
      if (this.sound && this.sound.playing()) {
        this.sound.pause();
      }
    }
  },
  mounted() {
    this.loadAudio();
  },
  beforeUnmount() {
    if (this.sound) {
      this.sound.unload();
    }
  }
}
</script>
<template>
    <div>
      <button @click="playAudio">Play</button>
      <button @click="pauseAudio">Pause</button>
    </div>
  </template>
