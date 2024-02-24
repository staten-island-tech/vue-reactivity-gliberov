<template>
    <div class="piano">
    <button
      v-for="key in keys"
      :key="key.note"
      @click="playNote(key.note)"
       :class="['piano-key', { 'black': key.note.includes('sharp') }]"
    >
      {{ key.label }}
    </button>
    </div>
    <button @click="replayMelodic" class="replay">Play Melodic!</button>
    <button @click="replayChord" class="replay">Play Chord!</button>
    <button @click="reset" class="reset">Reset Sequence!</button>
    <div class="chord">
    <p v-if="Chord.length === 0">No notes played</p>
    <p v-else>Sequence: {{ Chord.join(', ') }}</p>
  </div>
</template>

<script>
    export default {
        name: 'Piano',
        data() {
            return {
            keys: [
            { note: 'C3', label: 'C3' },
            { note: 'C3sharp', label: 'C#3' },
            { note: 'D3', label: 'D3' },
            { note: 'D3sharp', label: 'D#3' },
            { note: 'E3', label: 'E3' },
            { note: 'F3', label: 'F3' },
            { note: 'F3sharp', label: 'F#3' },
            { note: 'G3', label: 'G3' },
            { note: 'G3sharp', label: 'G#3' },
            { note: 'A3', label: 'A3' },
            { note: 'A3sharp', label: 'A#3' },
            { note: 'B3', label: 'B3' },
            { note: 'C4', label: 'C4' },
            { note: 'C4sharp', label: 'C#4' },
            { note: 'D4', label: 'D4' },
            { note: 'D4sharp', label: 'D#4' },
            { note: 'E4', label: 'E4' },
            { note: 'F4', label: 'F4' },
            { note: 'F4sharp', label: 'F#4' },
            { note: 'G4', label: 'G4' },
            { note: 'G4sharp', label: 'G#4' },
            { note: 'A4', label: 'A4' },
            { note: 'A4sharp', label: 'A#4' },
            { note: 'B4', label: 'B4' },
            { note: 'C5', label: 'C5' }
            ],
            Chord: []

            }
        },
        methods: {
            playNote(note) {
            const audio = new Audio(`/public/notes/${note}.ogg`)
            audio.play()
            this.Chord.push(note)
            const pressedKey = document.querySelector(`[data-note="${note}"]`)
            
            if (pressedKey) {
                pressedKey.classList.add('pressed')
                setTimeout(() => {
                pressedKey.classList.remove('pressed') }, 300)
                }
            },
            
            replayChord() {
                this.Chord.forEach(note=> {
                    const audio = new Audio(`/public/notes/${note}.ogg`)
                audio.play()
                })
            },

            replayMelodic() {
            this.Chord.forEach((note, index) => {
                setTimeout(() => {
                const audio = new Audio(`/public/notes/${note}.ogg`)
                audio.play()
                }, index * 500)
            });
            },

            reset() {
                this.Chord = []
            }
        } 
    }

</script>

<style lang="css" scoped>
.piano{
  display: flex;
}

.piano-key {
  width: 50px;
  height: 150px;
  background-color: #ccc;
  border: 1px solid #999;
  margin-right: 5px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
}

.piano-key.black {
  position: relative;
  width: 30px;
  height: 120px;
  background-color: #000; 
  border: 1px solid #999;
  cursor: pointer;
  z-index: 1;
  margin-left: -15px;}
.piano-key:not(.black) {
  z-index: 2;
}

.piano-key:hover {
  background-color: #ddd; 
}
.pressed {
  background-color: #ffcc00;
}
</style>