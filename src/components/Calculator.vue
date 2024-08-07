<template>
    <div class="container mt-2">
        <div class="card bg-dark mx-auto" style="max-width: 400px;">
            <div class="card-body text-white fw-4">
                <h2 class="card-title text-center">Calculadora</h2>
                <form @input="calculate">
                    <div class="mb-3">
                        <label for="operation" class="form-label">Operação</label>
                        <select class="form-select" v-model="operation">
                            <option value="add">Adição +</option>
                            <option value="subtract">Subtração -</option>
                            <option value="multiply">Multiplicação X</option>
                            <option value="divide">Divisão /</option>
                        </select>
                    </div>
                    <div class="mb-3">
                        <label for="num1" class="form-label">Número 1</label>
                        <input type="number" class="form-control" id="num1" v-model.number="num1"
                            placeholder="Digite o primeiro número">
                    </div>
                    <div class="mb-3">
                        <label for="num2" class="form-label">Número 2</label>
                        <input type="number" class="form-control" id="num2" v-model.number="num2"
                            placeholder="Digite o segundo número">
                    </div>

                    <div class="mt-3">
                        <h3 class="text-center">Resultado: {{ result }}</h3>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            num1: 0,
            num2: 0,
            operation: 'add',
            result: 0,
        };
    },
    methods: {
        calculate() {
            switch (this.operation) {
                case 'add':
                    this.result = this.num1 + this.num2;
                    break;
                case 'subtract':
                    this.result = this.num1 - this.num2;
                    break;
                case 'multiply':
                    this.result = this.num1 * this.num2;
                    break;
                case 'divide':
                    this.result = this.num1 / this.num2;
                    break;
            }
        },
    },
};
</script>

<style scoped>
.container {
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: center;

    height: 100vh;
}

.card {
    width: 100%;
    height: 60vh;
}
</style>