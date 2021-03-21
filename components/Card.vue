<template>
  <div
    :id="id"
    class="card rounded-lg w-1/2"
    :draggable="draggable"
    @dragstart="dragStart"
    @dragover.capture.prevent
    @drop.capture.prevent="drop"
  >
    {{ pieceVal }}
  </div>
</template>
<script>
export default {
  props: ["id", "draggable", "pieceValue"],
  data: function () {
    return {
      pieceVal: "",
      value: this.pieceValue,
      nameEquivalence: [
        "school",
        "clubs",
        "students",
        "officers",
        "president",
        "teacher",
        "program_head",
        "admin",
        "dean",
        "finance",
        "osa",
        "oic",
        "mayor",
        "ched",
        "school_pub",
      ],
    };
  },
  methods: {
    findPiece(piece) {
      return [this.nameEquivalence[piece], piece];
    },
    dragStart(e) {
      const target = e.target;
      e.dataTransfer.setData("card_value", this.value);
      e.dataTransfer.setData("card_id", target.id);
      setTimeout(() => {
        target.style.display = "none";
      }, 0);
    },
    drop(e) {
      const card_value = e.dataTransfer.getData("card_value");
      this.pieceVal = this.attack(card_value, this.value)[0];
      this.value = this.attack(card_value, this.value)[1];
    },
    attack(predator, prey) {
      if (predator === 15 && prey === 2) {
        return this.findPiece(prey);
      } else if (predator === 15 && prey < predator && prey !== 2) {
        return this.findPiece(predator);
      } else if (predator === 0 && prey === 0) {
        return this.findPiece(predator);
      } else if (predator === prey) {
        return null;
      } else if (predator > prey) {
        return this.findPiece(predator);
      } else {
        return this.findPiece(prey);
      }
    },
  },

  mounted() {
    this.pieceVal = this.findPiece(this.value)[0];
  },
};
</script>
