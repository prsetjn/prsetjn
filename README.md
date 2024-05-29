import openai
import requests

# Configura tu clave API de OpenAI
openai.api_key = 'YOUR_OPENAI_API_KEY'

# Descripción detallada para el avatar del búho
descripcion = """
Crea un avatar de un búho antropomorfizado que represente las carreras de Administración, Contabilidad, Enfermería y Farmacia. 
El búho debe llevar un pequeño maletín o una corbata (Administración), una calculadora o un gráfico financiero (Contabilidad), 
un gorro de enfermera o un estetoscopio (Enfermería), y un frasco de medicamentos o una bata blanca (Farmacia). 
El avatar debe ser amistoso y profesional.
"""

# Crear avatar usando una API de generación de imágenes
def crear_avatar(descripcion):
    # Aquí usarías una API de generación de imágenes como DALL-E, Midjourney o Stable Diffusion.
    # Este es un ejemplo con una API ficticia
    url = "https://api.generador-de-imagenes.com/v1/create"
    headers = {
        "Authorization": "Bearer YOUR_IMAGE_API_KEY",
        "Content-Type": "application/json"
    }
    data = {
        "prompt": descripcion,
        "size": "512x512"
    }
    response = requests.post(url, headers=headers, json=data)
    if response.status_code == 200:
        return response.json()["image_url"]
    else:
        return None

# Generar y mostrar el avatar
url_avatar = crear_avatar(descripcion)
print(f"Avatar generado: {url_avatar}")
