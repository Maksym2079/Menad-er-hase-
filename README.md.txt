
# Menadżer Haseł – Bezpieczna aplikacja webowa do przechowywania haseł

## Autorzy
**Bohdan Krasnitskyi**, **Maksym Kryskiv**, **Iryna Kravchuk** 
Przedmiot: Cyberbezpieczeństwo  
Prowadzący: **dr inż. Łukasz Jeleń**

---

## 1. Cel projektu

Celem projektu jest stworzenie bezpiecznej aplikacji webowej, umożliwiającej użytkownikom generowanie, zapisywanie i zarządzanie swoimi hasłami w sposób zaszyfrowany. Projekt rozwiązuje problem stosowania słabych, powtarzalnych haseł oraz ich nieprawidłowego przechowywania.

---

## 2. Zakres projektu

W ramach projektu zaimplementowano:

- rejestrację i logowanie użytkownika,
- bezpieczne przechowywanie haseł w bazie danych,
- generator silnych haseł,
- mechanizmy szyfrowania haseł,
- interfejs użytkownika oparty o HTML/CSS.

---

## 3. Opis ogólny

Zarządzanie hasłami to kluczowy element cyberbezpieczeństwa. W dobie rosnącej liczby kont internetowych użytkownicy często powielają swoje hasła, co zwiększa ryzyko włamania. Menadżer haseł pozwala generować trudne do złamania hasła i przechowywać je bezpiecznie, eliminując konieczność ich zapamiętywania.

Podczas gdy narzędzia komercyjne takie jak LastPass, Bitwarden czy KeePass oferują zaawansowane funkcje, nasz projekt stanowi edukacyjną alternatywę — prostą aplikację webową z podstawową funkcjonalnością.

---

## 4. Technologia

- **Język programowania**: Python  
- **Framework**: Flask  
- **Baza danych**: SQLite  
- **Szyfrowanie haseł**: `werkzeug.security` (scrypt), opcjonalnie `bcrypt`  
- **Frontend**: HTML5, CSS3  
- **Inne narzędzia**: `venv`, Flask-WTF, Flask-Login, Werkzeug

---

## 5. Funkcje aplikacji

Aplikacja umożliwia:

- bezpieczną rejestrację i logowanie użytkowników,
- haszowanie haseł za pomocą bezpiecznego algorytmu,
- generowanie losowych, silnych haseł (moduł `secrets`),
- przechowywanie haseł w bazie danych powiązanej z użytkownikiem,
- prosty i czytelny interfejs użytkownika.

---

## 6. Struktura projektu

```
password_manager/
│
├── templates/
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   └── add_password.html
│
├── static/
│   └── styles.css (opcjonalnie)
│
├── app.py
├── requirements.txt
└── passwords.db (generowany automatycznie)
```

---

## 7. Potencjalne problemy i rozwiązania

| Problem | Rozwiązanie |
|--------|-------------|
| Problemy z szyfrowaniem haseł | Testowanie z użyciem `bcrypt` i `werkzeug.security` |
| Trudności z zarządzaniem sesjami | Użycie `Flask-Login` do obsługi sesji użytkowników |
| Bezpieczeństwo formularzy (np. CSRF) | Włączenie zabezpieczeń CSRF przez Flask-WTF |

---

## 8. Uruchomienie aplikacji

### 1. Sklonuj repozytorium

```bash
git clone https://github.com/Maksym2079/Menad-er-hase-.git
cd password-manager
```

### 2. Utwórz środowisko wirtualne

```bash
python -m venv venv
source venv/bin/activate  # Na Windows: venv\Scripts\activate
```

### 3. Zainstaluj zależności

```bash
pip install -r requirements.txt
```

### 4. Uruchom aplikację

```bash
python app.py
```

Otwórz przeglądarkę i przejdź do `http://127.0.0.1:5000`.

---

## 9. Literatura

- [Dokumentacja Flask](https://flask.palletsprojects.com/)
- [Dokumentacja bcrypt](https://pypi.org/project/bcrypt/)
- [OWASP – Best Practices for Password Storage](https://owasp.org/)
- [RealPython – Flask Tutorials](https://realpython.com)

---

## 10. Licencja

Projekt stworzony w celach edukacyjnych.
