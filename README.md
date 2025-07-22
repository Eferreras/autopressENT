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
