<template src="../views/ProyeccionConsumoTable.html"></template>

<script>
import "../assets/ProyeccionConsumoTable.css";
export default {
    data() {
        return {
            searchQuery: "",
            selectedPrioridad: "",
            proyecciones: [
                { fecha: '2024-02-01', producto: 'Laptop ASUS', proyeccionAnterior: 15, realConsumida: 10, desviacion: '-5' },
                { fecha: '2024-02-05', producto: 'Camiseta Nike', proyeccionAnterior: 60, realConsumida: 50, desviacion: '-10' },
                { fecha: '2024-02-10', producto: 'Smartphone Samsung', proyeccionAnterior: 7, realConsumida: 5, desviacion: '-2' },
                { fecha: '2024-02-15', producto: 'Pan Bimbo', proyeccionAnterior: 120, realConsumida: 100, desviacion: '-20' }
            ]
        };
    },
    computed: {
        filteredProyecciones() {
            let filtered = this.proyecciones.filter(proyeccion =>
                proyeccion.producto.toLowerCase().includes(this.searchQuery.toLowerCase())
            );
            return filtered;
        }
    }
};
</script>
