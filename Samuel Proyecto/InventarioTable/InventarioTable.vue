<template src="../views/InventarioTavble.html"></template>


<script>
import "../assets/InventarioTable.css";
export default {
    data() {
        return {
            searchQuery: "",
            selectedPrioridad: "",
            productos: [
                { nombre: 'Laptop ASUS', stock: 10, necesaria: 20, consumo: 'Alta', fechaRecomendada: '2024-03-01', prioridad: 'Alta' },
                { nombre: 'Camiseta Nike', stock: 50, necesaria: 40, consumo: 'Media', fechaRecomendada: '2024-03-10', prioridad: 'Media' },
                { nombre: 'Smartphone Samsung', stock: 5, necesaria: 15, consumo: 'Alta', fechaRecomendada: '2024-03-05', prioridad: 'Alta' },
                { nombre: 'Pan Bimbo', stock: 100, necesaria: 80, consumo: 'Baja', fechaRecomendada: '2024-02-28', prioridad: 'Baja' }
            ]
        };
    },
    computed: {
        filteredProductos() {
            let filtered = this.productos.filter(producto =>
                producto.nombre.toLowerCase().includes(this.searchQuery.toLowerCase())
            );
            if (this.selectedPrioridad) {
                filtered = filtered.filter(p => p.prioridad === this.selectedPrioridad);
            }
            return filtered;
        }
    },
    methods: {
        editarProducto(index) {
            alert(`Editar producto: ${this.productos[index].nombre}`);
        },
        eliminarProducto(index) {
            if (confirm(`¿Seguro que quieres eliminar ${this.productos[index].nombre}?`)) {
                this.productos.splice(index, 1);
            }
        },
        verProducto(index) {
            alert(`Ver detalles de: ${this.productos[index].nombre}`);
        }
    }
};
</script>