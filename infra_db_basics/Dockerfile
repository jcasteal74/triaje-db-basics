# Usa una imagen oficial de Python
#
# Imagen generada el 20250214 para desarrollo de db triaje.
#
#
FROM python:3.12-slim

# Establece el directorio de trabajo en el contenedor
WORKDIR /app

# Actualiza los paquetes e instala las dependencias del sistema necesarias
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    default-mysql-client \
    libmariadb-dev && \
    rm -rf /var/lib/apt/lists/*

# Instala los paquetes de Python más usados en ciencia de datos
RUN pip install --no-cache-dir \
    jupyterlab \
    pandas \
    numpy \
    matplotlib \
    seaborn \
    scikit-learn \
    scipy \
    statsmodels \
    ipywidgets \
    notebook \
    plotly \
    openpyxl \
    xlrd \
    pymysql \
    mariadb

# Expone el puerto en el que correrá JupyterLab
EXPOSE 8888

# Establece el comando de arranque para JupyterLab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]