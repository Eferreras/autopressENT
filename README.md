AutoEnter
Descripción
AutoEnter es un script en Python que automatiza la presión de la tecla Enter en intervalos cortos (50 ms). El programa permite iniciar la automatización tras un retraso de 5 segundos y se puede detener manualmente presionando la tecla 'q'. Utiliza las bibliotecas pyautogui y keyboard para controlar el teclado y detectar entradas del usuario.
Este script es útil para tareas repetitivas que requieren presionar Enter continuamente, como en formularios, pruebas de software o automatización de procesos.

Características
Presiona la tecla Enter automáticamente cada 50 milisegundos.
Incluye un retraso inicial de 5 segundos antes de comenzar.
Se detiene al presionar la tecla 'q'.
Incorpora la función FAILSAFE de pyautogui para mayor seguridad (mueve el ratón a la esquina superior izquierda para detener el script).
Manejo de errores para una ejecución robusta.

Tecnologías Utilizadas
Python 3.x
Bibliotecas:
pyautogui: Para simular pulsaciones de teclas.
keyboard: Para detectar la tecla 'q' y detener el programa.
time: Para gestionar retrasos y pausas.

Requisitos
Python 3.6 o superior.
Bibliotecas necesarias:
pip install pyautogui keyboard

Instalación
Clona el repositorio:
git clone https://github.com/tu_usuario/autoenter.git
Navega al directorio del proyecto:
cd autoenter
Instala las dependencias:
pip install -r requirements.txt

Uso
Ejecuta el script:
python autoenter.py
El programa esperará 5 segundos antes de comenzar a presionar Enter.
Presiona la tecla 'q' para detener la ejecución en cualquier momento.
Como medida de seguridad, mueve el ratón a la esquina superior izquierda de la pantalla para activar el FAILSAFE de pyautogui y detener el script.

Advertencias
Uso responsable: Este script simula pulsaciones de teclas y puede interferir con otras aplicaciones. Úsalo con precaución.
Permisos: En algunos sistemas operativos, keyboard puede requerir permisos de administrador para detectar teclas.
FAILSAFE: Mantén habilitada la función FAILSAFE de pyautogui para evitar problemas. Mueve el ratón a la esquina superior izquierda si el script no responde.

Contribuciones
¡Las contribuciones son bienvenidas! Si deseas mejorar este proyecto:
Haz un fork del repositorio.
Crea una rama para tu funcionalidad (git checkout -b nueva-funcionalidad).
Realiza los cambios y haz commit (git commit -m "Añadir nueva funcionalidad").
Envía un pull request.

Licencia
Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

Contacto
Si tienes preguntas o sugerencias, contáctame en hopestudiosdr@gmail.com
---------------------------------------------------------------------------------------------------------------------------


import pyautogui
import time
import keyboard

def main():
    pyautogui.PAUSE = 0.1
    pyautogui.FAILSAFE = True

    print("El programa comenzará a presionar Enter en 5 segundos. Presiona 'q' para detener.")
    time.sleep(5)

    try:
        while True:
            if keyboard.is_pressed('q'):
                print("Programa detenido por el usuario.")
                break
            pyautogui.press('enter')
            time.sleep(0.05)
    except Exception as e:
        print(f"Ocurrió un error: {e}")
    finally:
        print("Programa finalizado.")

if __name__ == "__main__":
    main()
