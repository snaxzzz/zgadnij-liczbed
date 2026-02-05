import random

najlepszy_wynik = None

while True:
    sekret = random.randint(1, 100)
    proby = 0

    print("\n--- Zgadnij liczbę ---")
    print("Zgadnij liczbę od 1 do 100")

    while True:
        try:
            strzal = int(input("Podaj liczbę: "))
        except ValueError:
            print("To nie liczba!")
            continue

        proby += 1

        if strzal < sekret:
            print("Za mało!")
        elif strzal > sekret:
            print("Za dużo!")
        else:
            print(f"Brawo! Zgadłeś w {proby} próbach!")

            if najlepszy_wynik is None or proby < najlepszy_wynik:
                najlepszy_wynik = proby
                print("🔥 Nowy rekord!")

            break

    print("Najlepszy wynik:", najlepszy_wynik)

    again = input("Grasz jeszcze raz? (t/n): ")
    if again.lower() == "n":
        break
