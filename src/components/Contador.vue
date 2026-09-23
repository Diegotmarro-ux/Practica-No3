<script setup lang="ts">
import { ref } from 'vue'

const contador = ref<number>(0)

function incrementar(): void {
  contador.value++
}

function decrementar(): void {
  contador.value--
}

function reiniciar(): void {
  contador.value = 0
}
</script>

<template>
  <div class="card shadow p-4 rounded-4" style="min-width: 340px;">
    <div class="card-body text-center">
      <h2 class="fw-semibold text-dark mb-3" style="font-size: 1.1rem;">Valor actual</h2>

      <div class="rounded-3 py-4 mb-4 bg-light">
        <p class="display-3 fw-bold text-dark m-0">{{ contador }}</p>
      </div>

      <div class="d-flex justify-content-center gap-3">
        <div class="text-center">
          <button
            class="btn btn-danger rounded-circle fw-bold fs-4 d-flex align-items-center justify-content-center btn-animado"
            style="width: 60px; height: 60px;"
            @click="decrementar"
            aria-label="Decrementar"
          >
            −
          </button>
          <p class="small text-muted mt-2 mb-0">Decrementar</p>
        </div>

        <div class="text-center">
          <button
            class="btn btn-success rounded-circle fw-bold d-flex align-items-center justify-content-center btn-animado"
            style="width: 60px; height: 60px; font-size: 1.3rem;"
            @click="reiniciar"
            aria-label="Reiniciar"
          >
            ↻
          </button> 
          <p class="small text-muted mt-2 mb-0">Reiniciar</p>
        </div>

        <div class="text-center">
          <button
            class="btn btn-primary rounded-circle fw-bold fs-4 d-flex align-items-center justify-content-center btn-animado"
            style="width: 60px; height: 60px;"
            @click="incrementar"
            aria-label="Incrementar"
          >
            +
          </button>
          <p class="small text-muted mt-2 mb-0">Incrementar</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.btn-animado {
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}

.btn-animado:hover {
  transform: translateY(-4px) scale(1.05);
  box-shadow: 0 6px 14px rgba(0, 0, 0, 0.2);
}

.btn-animado:active {
  transform: scale(0.9);
  transition: transform 0.08s ease;
}
</style>
