# Samaruc Plugin Marketplace

Repositorio oficial de plugins para Samaruc IDE - Entorno de desarrollo integrado para programación en C y Assembly para sistemas de 8 bits.

## Sobre Samaruc IDE

Samaruc es un IDE especializado en el desarrollo de software para arquitecturas clásicas de 8 bits. Este marketplace proporciona plugins que extienden las capacidades del IDE con compiladores, debuggers, emuladores y herramientas específicas.

## Estructura del Repositorio

```
plugins-repo/
├── plugins.json              # Registro principal de plugins
├── plugins/                 # Directorio de archivos .jar
│   ├── toolchains/          # Kits de desarrollo (GBDK, Z88DK, CC65)
│   ├── graphic-tools/       # Herramientas gráficas (sprites, tiles)
│   ├── sound-tools/         # Herramientas de audio (trackers, SFX)
│   └── translation-tools/   # Herramientas de traducción
├── docs/                   # Documentación de plugins
├── schema.json            # Schema de validación JSON
└── README.md             # Este archivo
```

## Arquitecturas Soportadas

### Procesadores Clásicos:
- Z80 - Zilog Z80 y compatibles (MSX, ZX Spectrum, etc.)


### Sistemas y Consolas:
- Game Boy


## Categorías de Plugins

| Categoría | Descripción | Ejemplos |
|-----------|-------------|----------|
| toolchains | Kits de desarrollo completos | GBDK, Z88DK, CC65, NESdev |
| graphic-tools | Editores gráficos y herramientas visuales | Sprite editors, tile editors, convertidores |
| sound-tools | Herramientas de audio y música | Music trackers, SFX generators, convertidores |
| translation-tools | Herramientas de localización | Text extractors, font editors, ROM tools |
## Formato del archivo plugins.json

El archivo plugins.json contiene toda la metadata de los plugins disponibles:

```json
{
  "marketplace": {
    "name": "Samaruc Plugin Marketplace",
    "version": "1.0.0",
    "lastUpdated": "2026-04-14T00:00:00Z",
    "description": "Marketplace para Samaruc IDE - Desarrollo C/Assembly 8-bit"
  },
  "plugins": {
    "editor-tiles-gbdk": {
      "name": "Editor de Tiles GBDK",
      "version": "1.0.0", 
      "description": "Editor de tiles para Game Boy Development Kit",
      "author": "Samaruc Team",
      "category": "graphic-tools",
      "tags": ["gameboy", "tiles", "gbdk", "graphics"],
      "downloadUrl": "https://raw.githubusercontent.com/tu-usuario/plugins-repo/main/plugins/graphic-tools/editor-tiles-gbdk-1.0.0.jar",
      "minSamarucVersion": "1.0.0",
      "dependencies": [],
      "releaseDate": "2026-04-14"
    },
    "lsdpatch-plugin": {
      "name": "LSDPatch Plugin",
      "version": "1.0.0",
      "description": "Plugin para patcheo y modificación de archivos de sonido LSD",
      "author": "Samaruc Team", 
      "category": "sound-tools",
      "tags": ["lsd", "sound", "patch", "chiptune"],
      "downloadUrl": "https://raw.githubusercontent.com/tu-usuario/plugins-repo/main/plugins/sound-tools/lsdpatch-plugin-1.0.0.jar",
      "minSamarucVersion": "1.0.0",
      "dependencies": [],
      "releaseDate": "2026-04-14"
    }
  },
  "categories": {
    "toolchains": {
      "name": "Toolchains",
      "description": "Kits de desarrollo completos para 8-bit"
    },
    "graphic-tools": {
      "name": "Herramientas Gráficas",
      "description": "Editores gráficos y herramientas visuales"
    },
    "sound-tools": {
      "name": "Herramientas de Sonido", 
      "description": "Herramientas de audio y música"
    },
    "translation-tools": {
      "name": "Herramientas de Traducción",
      "description": "Herramientas de localización"
    }
  }
}
```

## Cómo Agregar un Plugin

1. Desarrollar el plugin para Samaruc IDE (archivo .jar)
2. Elegir la categoría apropiada según la funcionalidad
3. Subir el .jar a la carpeta: plugins/categoria/
4. Actualizar plugins.json con la información completa
5. Crear documentación (opcional) en docs/
6. Hacer commit y push de los cambios

### Nomenclatura recomendada para archivos .jar:

Para toolchains:
```
plataforma-toolchain-version.jar
Ejemplos: gbdk-toolchain-4.1.1.jar, z88dk-toolkit-2.2.0.jar
```

Para herramientas gráficas:
```
tipo-herramienta-version.jar  
Ejemplos: gb-sprite-editor-2.1.0.jar, nes-chr-editor-1.8.5.jar
```

Para herramientas de sonido:
```
plataforma-tipo-version.jar
Ejemplos: gb-music-tracker-2.3.0.jar, nes-famitracker-plugin-1.8.2.jar
```

Para herramientas de traducción:
```
tipo-plataforma-version.jar
Ejemplos: text-extractor-gb-2.1.0.jar, font-editor-nes-1.5.3.jar
```

### Requisitos específicos:
- El plugin debe ser compatible con Samaruc IDE
- Debe soportar desarrollo para sistemas de 8 bits
- Seguir las convenciones de naming específicas por categoría
- Incluir documentación básica de uso
- Testear en al menos una plataforma objetivo

## Consumo del Marketplace

Samaruc puede consumir este marketplace accediendo a:
```
https://raw.githubusercontent.com/tu-usuario/plugins-repo/main/plugins.json
```

## API del Marketplace

### Obtener lista de todos los plugins:
```http
GET https://raw.githubusercontent.com/tu-usuario/plugins-repo/main/plugins.json
```

### Descargar un plugin:
```http
GET https://raw.githubusercontent.com/tu-usuario/plugins-repo/main/plugins/categoria/plugin.jar
```

## Contribuciones

1. Fork del repositorio
2. Crea una rama para tu plugin: `git checkout -b nuevo-plugin`
3. Agrega tu plugin siguiendo la estructura
4. Actualiza el plugins.json
5. Crea un Pull Request

## Licencia

Este marketplace está bajo licencia MIT. Cada plugin puede tener su propia licencia.

## Soporte

¿Problemas con un plugin? Crea un [issue](https://github.com/tu-usuario/plugins-repo/issues) en este repositorio.
