# Zadanie 1 — PAwChO (część obowiązkowa)

Autor: **Jakub Górecki**

Repozytorium GitHub: [https://github.com/JakubGoreckii/zadanie1](https://github.com/JakubGoreckii/zadanie1)  
Repozytorium DockerHub: [https://hub.docker.com/r/goras1234/zadanie1](https://hub.docker.com/r/goras1234/zadanie1)

---

## Opis

Aplikacja napisana w Pythonie (Flask), pozwala wybrać kraj i miasto z listy, a następnie pokazuje pogodę pobieraną z **Open-Meteo API**. Po starcie loguje:
- datę i godzinę uruchomienia,
- imię i nazwisko autora,
- numer portu (5000).

---

## Kod źródłowy

- **app.py** — serwer Flask, logowanie danych, obsługa wyboru i wyświetlania pogody.
- **requirements.txt** — zależności Python.
- **templates/index.html** — frontend HTML z formularzem.
- **Dockerfile** — wieloetapowy build Dockera z metadanymi autora i healthcheckiem.

---

## Polecenia Docker

### a) Budowanie obrazu
```bash
docker build -t zadanie1 .
```

### b) Uruchamianie kontenera
```bash
docker run -d -p 5000:5000 --name zadanie1_container zadanie1
```

### c) Uzyskanie logów aplikacji
```bash
docker logs zadanie1_container
```

### d) Sprawdzenie liczby warstw i rozmiaru obrazu
```bash
docker image inspect zadanie1 --format='{{json .RootFS.Layers}}'
docker image inspect zadanie1 --format='{{.Size}}'
```

---

## Działanie systemu

Po uruchomieniu kontenera przejdź do:
```
http://localhost:5000
```

Zrzut ekranu potwierdzający działanie aplikacji znajduje się w repozytorium.

---

## Uwagi

- Obraz Dockera zawiera metadane zgodne z OCI.
- Pogoda pobierana jest w czasie rzeczywistym z Open-Meteo.
