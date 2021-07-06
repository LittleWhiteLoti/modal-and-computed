<template>
    <div class="modal-bg">
        <div class="modal">
            <div>
                <input type="text" v-model="fetchPerson" />
                <span>Name: {{ name }} - Age: {{ age }}</span>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data() {

        let name
        let age

        return {
            name,
            age
        }
    },
    computed: {
        fetchPerson: {
            get() {
                return this.name
            },
            set(newValue) {
                let data = fetch("https://api.agify.io?name=" + newValue)

                data.then((response) => {
                    return response.json()
                })
                .then((json) => {
                    this.name = json.name
                    this.age = json.age
                })
            }
        }
    }
}

</script>

<style scoped>

.modal-bg {
    inset: 0;
    background: rgb(0, 99, 30);
    height: 50px;
}

.modal {
    display: flex;
    justify-content: center;
    align-items: center;
    color: red;
}

</style>