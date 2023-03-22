# Cometa Overflow

Este proyecto utiliza el modelo GPT-3 de OpenAI para indexar y buscar información en archivos dentro de un directorio. Estos archivos deben tener texto principalmente y pueden tener la extension `.md`.

## Requisitos previos

- Python 3.6 o posterior
- Clave de API de OpenAI

## Configuración y ejecución

1. **Crea un nuevo directorio para tu proyecto y navega a él en la terminal**:
    ```
    cd cometa-overflow/
    ```
2. **Crea un entorno virtual de Python para aislar las dependencias de tu proyecto**:
    ```bash
    virtualenv env
    ```
3. **Activa el entorno virtual**:

    En Windows:

    ```bash
    env\Scripts\activate
    ```

    En macOS o Linux:

    ```bash
    source env/bin/activate
    ```
4. **Instala las dependencias del archivo `requirements.txt`**:
    ```
    pip install -r requirements.txt
    ```

5. **Reemplaza `"YOUR_API_KEY"` en el archivo `main.py` con tu clave de API de OpenAI**

## Consideraciones

Dentro de la carpeta `content` puedes dejar tus archivos a indexar.
**Si insertas directorios que tienen subdirectorios considera la indexacion recursiva**

En el siguiente ejemplo estaremos mirando **exclusivamente** los archivos `.md` e indexaremos el directorio de manera recursiva.

```python
documents = SimpleDirectoryReader(directory_path, recursive=True, required_exts=".md").load_data()
```

Sientete libre de cambiar la extension que necesitas y deshabilitar la indexacion recursiva.

La primera vez que ejecutes el script, descomenta la línea `construct_index('./content/')` para construir el índice a partir de los archivos en la carpeta `content`.

**Después de la primera ejecución, vuelve a comentar esta línea para evitar reconstruir el índice en cada ejecución.**


