# MVES-CO — Sistema de Alerta Temprana
## Riesgo de Contagio Financiero Intersectorial en Colombia
**Maestría en Analítica de Datos · Universidad Central · 2026**
**Autores:** Katy Pacheco Manchego · Julian Andres Firacative Varon

---

## Estructura del proyecto

```
mves_streamlit/
├── app.py                  ← App principal Streamlit (multipágina)
├── mves_data.py            ← Módulo de datos y cálculos (cacheados)
├── requirements.txt        ← Dependencias Python
├── README.md               ← Este archivo
├── .streamlit/
│   └── config.toml         ← Tema y configuración del servidor
└── datos/
    ├── icds_mensual_definitivo.csv   ← Panel ICDS mensual (ISE+GEIH+IPP+IPC+TPM)
    ├── ise_mensual.csv               ← ISE DANE por actividad
    ├── empleo_mensual.csv            ← GEIH ocupados por rama
    ├── ipp_mensual.csv               ← IPP variación anual
    ├── ipc_mensual.csv               ← IPC variación anual
    ├── tpm_mensual.csv               ← TPM BanRep mensual
    ├── leontief_macro.json           ← Inversa de Leontief (MIP 2019-2021)
    └── resultados_icds_star.csv      ← ICDS* ajustado por MIP
```

---

## Instalación local

```bash
# 1. Clonar / descomprimir el proyecto
cd mves_streamlit

# 2. Crear entorno virtual (recomendado)
python -m venv venv
source venv/bin/activate        # Linux/Mac
# venv\Scripts\activate         # Windows

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Ejecutar el dashboard
streamlit run app.py
```

El dashboard se abrirá automáticamente en `http://localhost:8501`

---

## Despliegue en Streamlit Community Cloud (gratuito)

1. Subir el proyecto completo a un repositorio GitHub
2. Ir a [share.streamlit.io](https://share.streamlit.io)
3. Conectar el repositorio y seleccionar `app.py` como archivo principal
4. El servicio instalará automáticamente las dependencias de `requirements.txt`
5. La URL pública quedará disponible para compartir con el comité de tesis

---

## Páginas del dashboard

| Página | Descripción |
|--------|-------------|
| 📊 Resumen ejecutivo | KPIs, estado actual de los 12 sectores, nivel de alerta |
| 📈 Sectores ICDS / ICDS* | Tabla comparativa, ranking, heatmap histórico |
| ⏱ Evolución temporal | Línea de tiempo por sector, comparación múltiple |
| 🔄 Regímenes Markov | Serie agregada, matriz de transición P, alertas t+1/t+2 |
| 🔗 Contagio MIP | Red de dependencias, multiplicadores de Leontief |
| 💥 Simulador de choque | Simula un choque en cualquier sector y ve la propagación |
| 📖 Metodología | Marco teórico, fórmulas, fuentes y limitaciones |

---

## Notebooks complementarios

Los notebooks Jupyter documentan el pipeline completo:
- `NB1_Preprocesamiento.ipynb` → Carga, limpieza, normalización y cálculo del ICDS
- `NB2_Modelo_MIP.ipynb` → Inversa de Leontief, ICDS*, simulación de choques
- `NB3_Markov_Switching.ipynb` → Estimación de regímenes y señales de alerta

---

## Cómo citar

Pacheco Manchego, K. & Firacative Varon, J.A. (2026).
*Sistema de Alerta Temprana para la Identificación del Riesgo de Contagio Financiero
entre Sectores Económicos en Colombia*.
Maestría en Analítica de Datos, Universidad Central.
