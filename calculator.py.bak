# calculator.py

from colorama import Fore, Style, init

# Инициализация colorama для корректной работы цветов в консоли (особенно на Windows)
init(autoreset=True)


def add(a: float, b: float) -> float:
    """Возвращает сумму двух чисел"""
    return a + b


def subtract(a: float, b: float) -> float:
    """Возвращает разность a - b"""
    return a - b


def multiply(a: float, b: float) -> float:
    """Возвращает произведение"""
    return a * b


def divide(a: float, b: float) -> float:
    """Возвращает результат деления a / b, если b ≠ 0"""
    if b == 0:
        raise ValueError("Деление на ноль запрещено!")
    return a / b


# Словарь для удобного вызова функций по символу операции
OPERATIONS = {
    "+": add,
    "-": subtract,
    "*": multiply,
    "/": divide,
}


def main():
    calc_art = """
  ____      _            _       
 / ___|__ _| | ___ _   _| | __ _ 
| |   / _` | |/ __| | | | |/ _` |
| |__| (_| | | (__| |_| | | (_| |
 \\____\\__,_|_|\\___|\\__,_|_|\\__,_|
"""

    print(Fore.CYAN + Style.BRIGHT + calc_art)
    print(Fore.CYAN + "✨ Добро пожаловать в Красивый Калькулятор! ✨")
    print(Fore.CYAN + "=" * 50)

    while True:
        try:
            a_input = input(
                Fore.YELLOW
                + "🔢 Введите первое число (или 'q' для выхода): "
                + Style.RESET_ALL
            )
            if a_input.strip().lower() in ("q", "quit", "выход"):
                print(Fore.GREEN + "До новых встреч! 😊")
                break

            a = float(a_input)

            op = input(
                Fore.YELLOW + "🧮 Выберите операцию (+, -, *, /): " + Style.RESET_ALL
            ).strip()
            if op not in OPERATIONS:
                print(Fore.RED + "⚠️  Неверная операция. Попробуйте снова.")
                continue

            b = float(
                input(Fore.YELLOW + "🔢 Введите второе число: " + Style.RESET_ALL)
            )
            result = OPERATIONS[op](a, b)

            print(
                Fore.GREEN + Style.BRIGHT + f"\n✅ Результат: {a} {op} {b} = {result}\n"
            )
            print(Fore.CYAN + "-" * 50)

        except ValueError as ve:
            if "could not convert" in str(ve) or "invalid literal" in str(ve):
                print(Fore.RED + "⚠️  Ошибка: введите корректное число.")
            else:
                print(Fore.RED + f"⚠️  Ошибка: {ve}")
        except KeyboardInterrupt:
            print(Fore.GREEN + "\n\nДо свидания! 👋")
            break
        except Exception as e:
            print(Fore.RED + f"💥 Неожиданная ошибка: {e}")


# Запуск интерфейса только если файл запущен напрямую (а не импортирован)
if __name__ == "__main__":
    main()
