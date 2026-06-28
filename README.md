# ⚡ ElectroMax - Distributed Database UI Prototype

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![Academic Project](https://img.shields.io/badge/Status-Academic_Project-success?style=for-the-badge)

Prototipo de Interfaz de Usuario (Mockup) diseñado para demostrar la **Transparencia de Distribución** y el manejo de **Esquemas de Fragmentación** en un Sistema de Bases de Datos Distribuidas (SBDD). 

El proyecto simula la operación transaccional de una cadena de electrodomésticos con autonomía local en dos nodos principales, manteniendo una estética de Modo Oscuro (Dark Mode) estricta en 2D.

---

## 📖 Índice
- [Contexto del Proyecto](#-contexto-del-proyecto)
- [Arquitectura de Fragmentación](#-arquitectura-de-fragmentación)
- [Características Principales](#-características-principales)
- [Instalación y Uso](#-instalación-y-uso)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Equipo de Desarrollo](#-equipo-de-desarrollo)

---

## 🎯 Contexto del Proyecto
Este frontend fue desarrollado como parte de la cátedra de **Bases de Datos Distribuidas** dictada por el Ing. Enrique Mafla en la Escuela Politécnica Nacional. 

El objetivo principal es materializar visualmente cómo un usuario final interactúa con un sistema distribuido sin conocer la ubicación física de los datos, mientras que a nivel administrativo se respetan las reglas de partición vertical, horizontal primaria y horizontal derivada.

---

## 🧩 Arquitectura de Fragmentación

El diseño de la UI refleja el siguiente esquema lógico de distribución entre la **Matriz Quito (UIO)** y la **Sucursal Guayaquil (GYE)**:

| Tipo de Fragmentación | Entidad Aplicada | Descripción en la UI |
| :--- | :--- | :--- |
| **Replicación Total** | `SEDES`, `ELECTRODOMESTICO` | Catálogos globales disponibles y sincronizados en ambos nodos. |
| **Vertical** | `CLIENTE` | Separación de vistas: Datos de Validación (Cédula), Marketing (Contacto) y Detalles por zona. |
| **Horizontal Primaria** | `INVENTARIO`, `VENTA` | Filtrado dinámico de tuplas donde `id_sede = 'UIO'` o `'GYE'`. |
| **Horizontal Derivada** | `DETALLE_VENTA` | Los detalles de factura se almacenan localmente mediante un *Semijoin* con la tabla `VENTA`. |

---

## ✨ Características Principales

- **Transparencia de Localización:** Formularios de Punto de Venta (POS) que ejecutan *Joins* simulados entre datos locales (Stock) y datos replicados (Catálogo).
- **Diseño Transaccional Maestro-Detalle:** Modales interactivos que simulan la atomicidad de generar una factura, descontar inventario y registrar detalles con preservación de precios históricos.
- **Autonomía Local:** Interfaces que demuestran que cada sucursal puede operar de manera independiente ante posibles particiones de red.
- **Zero-Config Stack:** Construido con HTML semántico y Tailwind CSS vía CDN para una ejecución inmediata sin dependencias de Node.js.

---

## 🚀 Instalación y Uso

Dado que el proyecto utiliza una arquitectura *Zero-Config* para facilitar su revisión y portabilidad, no requiere instalación de dependencias pesadas.

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/Davandres/InterfazUsuario-BDD.git](https://github.com/Davandres/InterfazUsuario-BDD.git)
