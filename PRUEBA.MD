# Guía para Configurar y Probar un Proyecto de TypeScript con ts-node

Este documento te guiará a través de la configuración de un proyecto de TypeScript con `ts-node`, así como la adición y ejecución de pruebas básicas.

## Índice

1. [Introducción](#introducción)
2. [Paso 1: Crear un Nuevo Proyecto](#paso-1-crear-un-nuevo-proyecto)
3. [Paso 2: Instalar TypeScript y ts-node](#paso-2-instalar-typescript-y-ts-node)
4. [Paso 3: Configurar TypeScript](#paso-3-configurar-typescript)
5. [Paso 4: Configurar Scripts en `package.json`](#paso-4-configurar-scripts-en-packagejson)
6. [Paso 5: Crear Archivos de Ejemplo](#paso-5-crear-archivos-de-ejemplo)
7. [Paso 6: Configurar y Ejecutar Pruebas](#paso-6-configurar-y-ejecutar-pruebas)
8. [Paso 7: Ejecutar el Proyecto](#paso-7-ejecutar-el-proyecto)

## Introducción

Este documento proporciona los pasos para configurar un proyecto básico de TypeScript con `ts-node` y para realizar pruebas básicas utilizando el framework de pruebas `jest`.

## Paso 1: Crear un Nuevo Proyecto

1. **Crear un directorio para tu proyecto y accede a él:**

    ```bash
    mkdir mi-proyecto-ts
    cd mi-proyecto-ts
    ```

2. **Inicializa un nuevo proyecto de Node.js:**

    ```bash
    npm init -y
    ```

    Esto creará un archivo `package.json` con la configuración predeterminada.

## Paso 2: Instalar TypeScript y ts-node

1. **Instalar TypeScript y ts-node como dependencias de desarrollo:**

    ```bash
    npm install typescript ts-node --save-dev
    ```

2. **Instalar los tipos para Node.js:**

    ```bash
    npm install @types/node --save-dev
    ```

## Paso 3: Configurar TypeScript

1. **Crear un archivo de configuración de TypeScript (`tsconfig.json`):**

    ```bash
    npx tsc --init
    ```

    Esto generará un archivo `tsconfig.json` con la configuración predeterminada. Puedes ajustarlo según tus necesidades. Aquí tienes una configuración básica de ejemplo:

    ```json
    {
      "compilerOptions": {
        "target": "es6",
        "module": "commonjs",
        "outDir": "./dist",
        "rootDir": "./src",
        "strict": true,
        "esModuleInterop": true,
        "skipLibCheck": true
      },
      "include": ["src/**/*.ts"],
      "exclude": ["node_modules"]
    }
    ```

## Paso 4: Configurar Scripts en `package.json`

1. **Añadir un script para ejecutar TypeScript usando `ts-node` en tu `package.json`:**

    Abre el archivo `package.json` y añade lo siguiente en la sección `scripts`:

    ```json
    "scripts": {
      "start": "ts-node src/index.ts",
      "test": "jest"
    }
    ```

    Esto te permitirá ejecutar tu proyecto con el comando `npm start` y ejecutar pruebas con `npm test`.

## Paso 5: Crear Archivos de Ejemplo

1. **Crear el directorio `src` y un archivo TypeScript de ejemplo:**

    ```bash
    mkdir src
    touch src/index.ts
    ```

2. **Editar `src/index.ts` con el siguiente contenido de ejemplo:**

    ```typescript
    console.log('¡Hola, mundo!');
    ```

## Paso 6: Configurar y Ejecutar Pruebas

1. **Instalar Jest y los tipos de Jest:**

    ```bash
    npm install jest ts-jest @types/jest --save-dev
    ```

2. **Configurar Jest para TypeScript:**

    Crea un archivo de configuración para Jest llamado `jest.config.js` en la raíz del proyecto con el siguiente contenido:

    ```js
    module.exports = {
      preset: 'ts-jest',
      testEnvironment: 'node',
      testMatch: ['**/src/**/*.test.ts'],
    };
    ```

3. **Crear un archivo de prueba:**

    Crea un archivo de prueba en el directorio `src`:

    ```bash
    touch src/index.test.ts
    ```

    Añade el siguiente código de prueba al archivo `src/index.test.ts`:

    ```typescript
    test('Debe pasar la prueba básica', () => {
      expect(true).toBe(true);
    });
    ```

4. **Ejecutar las pruebas:**

    ```bash
    npm test
    ```

    Deberías ver que las pruebas se ejecutan correctamente y pasan.

## Paso 7: Ejecutar el Proyecto

1. **Ejecuta el proyecto usando el comando `npm`:**

    ```bash
    npm start
    ```

    Deberías ver `¡Hola, mundo!` impreso en la consola.
