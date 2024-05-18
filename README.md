# Web Testing - Escenarios de prueba con Cypress y Cucumber

Autor: Andrés Guillermo López Hurtado

## **Introducción**

Este proyecto de pruebas automatizadas evalúa la funcionalidad del sitio web [Sauce Labs](https://saucelabs.com/) utilizando Cypress y Cucumber bajo la metodología BDD (Behavior-Driven Development). Se implementó el modelo de Page Object para organizar y mantener el código de manera eficiente.

## **Objetivos**

1. Evaluar la funcionalidad del sitio web Sauce Labs.
2. Validar el comportamiento del ingreso al sitio con credenciales válidas e incorrectas.
3. Identificar posibles problemas de seguridad al simular ingresos fallidos y bloqueo de usuarios.
4. Verificar la manipulación del carrito de compras, incluyendo agregar y eliminar productos.
5. Garantizar el correcto funcionamiento del check-out y la información personal.
6. Utilizar el modelo de Page Object para un código organizado y mantenible.

### **Instalación de Cypress**

1. Inicializar un proyecto npm:
    
    ```
    npm init
    ```
    
2. Instalar Cypress:
    
    ```
    npm install cypress --save-dev
    ```
    

### **Instalación de Cucumber**

1. Instalar el preprocessor de Cucumber:
    
    ```
    npm install @badeball/cypress-cucumber-preprocessor --save-dev
    
    ```
    
2. Instalar el empaquetador Esbuild:
    
    ```
    npm i -D cypress @bahmutov/cypress-esbuild-preprocessor esbuild --save-dev
    ```
    

### **Pruebas en paralelo**

1. Instalar la dependencia para pruebas en paralelo:
    
    ```
    npm i cypress-parallel
    
    ```
    
2. Configurar scripts en **`package.json`**:
    
    ```json
    "scripts": {
      "cy:run": "cypress run",
      "cy:parallel": "cypress-parallel -s cy:run -t 2 -d <your-cypress-specs-folder> -a '\"<your-cypress-cmd-args>\"'"
    }
    
    ```
    

## **Ejecución de las pruebas**

- Para ejecutar las pruebas:
    
    ```
    npx cypress run
    
    ```
    
- Para ejecutar en la interfaz gráfica:
    
    ```
    npm run cypress:runner
    ```
    

## Pipeline

Se desarrolla también un pequeño script .yml de tal manera que se las pruebas se puedan ejecutar de manera automática cumpliendo el objetivo de una retroalimentación ágil para el equipo de desarrollo y metodología que se esté utilizando, dicho script ejecuta a través de logs los features correspondientes de tal manera que se tenga una base de pruebas mantenible y escalable en el tiempo.
