# Práctica de Configuración de Entorno, Uso de Git y Lectura de Dataset en Python

## 1. Creación del entorno virtual en Windows (sin Anaconda)

```bash
python -m venv ml-env
```

### Activación del entorno (en Git Bash):

```bash
source ml-env/Scripts/activate
```

Resultado esperado:

```bash
(ml-env)
```

---

## 2. Instalación de librerías necesarias

Con el entorno virtual activo:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter notebook
```

---

## 3. Inicialización y uso de Git

```bash
git init
git add .
git commit -m "Primer notebook de prueba"
git remote add origin https://github.com/fjobando/practica-1.git  # Repositorio real
```

* Si da error de que origin ya existe:

```bash
git remote set-url origin https://github.com/fjobando/practica-1.git
```

### Cambio a rama principal:

```bash
git branch -M main
```

### Subida al repositorio:

```bash
git push -u origin main
```

---

## 4. Lectura de archivo CSV desde ruta absoluta en Windows

Ubicación del archivo:

```
D:\Curso DL\Practica 1\kaggle_top_100_dataset.csv
```

### Problemas encontrados:

* UnicodeDecodeError
* ParserError

### Solución final:

```python
import pandas as pd

df = pd.read_csv(r"D:\Curso DL\Practica 1\kaggle_top_100_dataset.csv", encoding="cp1252", sep=";")
print(df.head())
```

---

## 5. Ejecución de Jupyter Notebook

Desde terminal:

```bash
jupyter notebook
```

Se abre el navegador y se pueden crear notebooks para interactuar con el entorno y visualizar el dataset.

---

## Observaciones:

* Es importante usar `r"ruta"` o `\\` en rutas de Windows.
* Muchos CSV de Excel en configuración regional española usan `;` como delimitador.
* La autenticación con GitHub puede requerir el uso de Git Credential Manager.

---

Fin de la práctica.
