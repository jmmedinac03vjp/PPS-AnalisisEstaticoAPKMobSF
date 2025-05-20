# Análisis Estático de APK con MobSF: InsecureBankv2

Este repositorio contiene una guía paso a paso para realizar un análisis estático de una aplicación Android vulnerable, **InsecureBankv2**, utilizando la herramienta **Mobile Security Framework (MobSF)**.

## Índice

1. [¿Qué es MobSF?](#1-qué-es-mobsf)  
2. [Obtener InsecureBankv2](#2-obtener-insecurebankv2)  
3. [Instalar MobSF](#3-instalar-mobsf)  
4. [Acceder a MobSF](#4-acceder-a-mobsf)  
5. [Análisis estático con MobSF](#5-análisis-estático-con-mobsf)  
6. [Interpretación de resultados](#6-interpretación-de-resultados)  

---

## 1. ¿Qué es MobSF?

**Mobile Security Framework (MobSF)** es una herramienta automatizada todo en uno para análisis de seguridad de aplicaciones móviles (Android/iOS/Windows). MobSF permite realizar análisis **estático**, **dinámico** y **basado en API**, y está especialmente diseñado para pruebas de seguridad móviles en entornos DevSecOps.

### Características principales:

- Análisis estático de APK, AAB, IPA y código fuente.
- Análisis dinámico (sandbox automatizado).
- Análisis de binarios y API REST.
- Informes detallados de seguridad y recomendaciones.

> Sitio oficial: https://mobsf.github.io/docs/

---

## 2. Obtener InsecureBankv2

**InsecureBankv2** es una aplicación vulnerable desarrollada con fines educativos para practicar análisis y explotación de fallos en apps móviles.

### Pasos:

1. Clona el repositorio oficial:
   ```bash
   git clone https://github.com/dineshshetty/Android-InsecureBankv2.git
   ```

2. Compila el APK con Android Studio o utiliza una versión precompilada (si está disponible).

> ⚠️ **Nota:** Esta aplicación es intencionadamente insegura. No la instales en dispositivos personales o en entornos de producción.

---

## 3. Instalar MobSF

Puedes ejecutar MobSF localmente utilizando Docker o de forma manual. A continuación, se muestra el método recomendado (Docker):

### Opción 1: Usar Docker (recomendado)

```bash
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
cd Mobile-Security-Framework-MobSF
docker build -t mobsf .
docker run -it -p 8000:8000 mobsf
```

### Opción 2: Instalación manual

Sigue la guía oficial en: https://mobsf.github.io/docs/#/installation

---

## 4. Acceder a MobSF

Una vez iniciado MobSF (ya sea por Docker o manualmente), accede a través de tu navegador:

```
http://localhost:8000
```

Verás la interfaz web de MobSF, lista para analizar APKs.

---

## 5. Análisis estático con MobSF

### Pasos:

1. Accede a `http://localhost:8000`.
2. Arrastra el archivo `InsecureBankv2.apk` o selecciónalo manualmente.
3. Espera a que se complete el análisis (unos segundos/minutos).
4. Se generará un informe detallado automáticamente.

---

## 6. Interpretación de resultados

MobSF genera un informe con múltiples secciones, entre ellas:

- **Manifest Analysis**: Revisión de permisos, actividades exportadas, etc.
- **Code Analysis**: Identificación de código inseguro, API peligrosas, strings sensibles.
- **Security Score**: Puntuación general basada en vulnerabilidades encontradas.
- **Recommendations**: Buenas prácticas y sugerencias para corregir los fallos detectados.
- **Tracker/Library Detections**: Librerías de terceros potencialmente inseguras.

> Revisa especialmente los apartados que marcan hallazgos en rojo o con severidad alta.

---

## 📘 Recursos adicionales

- [MobSF Documentation](https://mobsf.github.io/docs/)
- [OWASP Mobile Top 10](https://owasp.org/www-project-mobile-top-10/)
- [InsecureBankv2 GitHub](https://github.com/dineshshetty/Android-InsecureBankv2)

---

## ⚠️ Disclaimer

Este proyecto se proporciona solo con fines educativos. El uso de herramientas como MobSF debe realizarse únicamente sobre aplicaciones propias o con autorización explícita.

---

## Autor

Repositorio creado por José Miguel Medina, para prácticas de análisis de seguridad móvil en el contexto de PPS (Puesta en Producción Segura).
