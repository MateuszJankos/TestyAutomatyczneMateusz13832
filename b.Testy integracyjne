import random
import unittest

class Bohater:
    def __init__(self, name, zdrowie, moc):
        self.name = name
        self.zdrowie = zdrowie
        self.moc = moc

    def Atak(self, cel):
        obrazenia = random.randint(1, self.moc)
        cel.zdrowie -= obrazenia
        print(f"{self.name} zaatakował {cel.name}a i zadał {obrazenia} obrażeń.")

    def is_alive(self):
        return self.zdrowie > 0

def wybierz_bohatera():
    print("Wybierz swojego bohatera:")
    print("1. Wojownik")
    print("2. Kusznik")
    print("3. Bard")
    print("4. Czarodziej")
    choice = input("Wybierz swojego bohatera wpisując od 1 do 4: ")

    if choice == "1":
        return Bohater("Wojownik", 120, 12)
    elif choice == "2":
        return Bohater("Kusznik", 80, 10)
    elif choice == "3":
        return Bohater("Bard", 100, 8)
    elif choice == "4":
        return Bohater("Czarodziej", 60, 15)
    else:
        print("Nieprawidłowa liczba. Wybrano za ciebie, bohater to Bober.")
        return Bohater("Bober", 200, 25)

def wybierz_przeciwnika():
    print("Wybierz swojego przeciwnika:")
    print("1. Krab")
    print("2. Dzik")
    print("3. Niedzwiedz")
    choice = input("Wybierz swojego przeciwnika wpisując od 1 do 3: ")

    if choice == "1":
        return Bohater("Krab", 40, 5)
    elif choice == "2":
        return Bohater("Dzik", 80, 10)
    elif choice == "3":
        return Bohater("Niedzwiedz", 150, 15)
    else:
        print("Nieprawidłowa liczba. Wybrano za ciebie, przeciwnik to Anty-bober.")
        return Bohater("Anty-bober", 210, 37)

def walka(gracz, przeciwnik):
    print(f"Wielka walka rozpoczyna sie pomiedzy {gracz.name} i {przeciwnik.name}!")
    while gracz.is_alive() and przeciwnik.is_alive():
        gracz.Atak(przeciwnik)
        if przeciwnik.is_alive():
            przeciwnik.Atak(gracz)

    if gracz.is_alive():
        print(f"{gracz.name} - Wygrywa walke!!!")
    else:
        print(f"{przeciwnik.name} - Wygrywa walke!!!")

class TestBohater(unittest.TestCase):
    def test_is_alive(self):
        bohater = Bohater("Test", 100, 10)
        self.assertTrue(bohater.is_alive())

        bohater.zdrowie = 0
        self.assertFalse(bohater.is_alive())

class TestWalka(unittest.TestCase):
    def test_walka(self):
        gracz = Bohater("TestGracz", 100, 10)
        przeciwnik = Bohater("TestPrzeciwnik", 100, 10)

        walka(gracz, przeciwnik)

        self.assertFalse(gracz.is_alive() and przeciwnik.is_alive())

# Wykonanie testów jednostkowych 10 razy
if __name__ == '__main__':
    for _ in range(10):
        suite = unittest.TestLoader().loadTestsFromTestCase(TestBohater)
        unittest.TextTestRunner(verbosity=2).run(suite)

    # Wykonanie testów integracyjnych 10 razy
    for _ in range(10):
        suite = unittest.TestLoader().loadTestsFromTestCase(TestWalka)
        unittest.TextTestRunner(verbosity=2).run(suite)

    # Wybór bohatera przez gracza
    gracz = wybierz_bohatera()

    # Wybór przeciwnika przez gracza
    przeciwnik = wybierz_przeciwnika()

    # Rozpoczęcie bitwy
    walka(gracz, przeciwnik)
