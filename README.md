# Guía para Configurar un Proyecto de TypeScript

Este documento te guiará a través de los pasos necesarios para configurar un proyecto de TypeScript con Node.js.

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

    Esto indica que el código TypeScript se encuentra en el directorio `src` y que la salida compilada se generará en `dist`.

## Paso 4: Configurar Scripts en `package.json`

1. **Añadir un script para ejecutar TypeScript usando `ts-node` en tu `package.json`:**

    Abre el archivo `package.json` y añade lo siguiente en la sección `scripts`:

    ```json
    "scripts": {
      "start": "ts-node src/index.ts"
    }
    ```

    Esto te permitirá ejecutar tu proyecto con el comando `npm start`.

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

## Paso 6: Ejecutar el Proyecto

1. **Ejecuta el proyecto usando el comando `npm`:**

    ```bash
    npm start
    ```

    Deberías ver `¡Hola, mundo!` impreso en la consola.
