# Zadanie 1 — Programowanie Aplikacji w Chmurze Obliczeniowej

Autor: **Jakub Górecki**

---

## Opis

Projekt wykonany w ramach części obowiązkowej Zadania 1.  
Aplikacja w Pythonie (Flask) działająca w kontenerze Docker.  
Po starcie loguje datę, autora i port, a w interfejsie web pozwala wybrać kraj i miasto i pokazać pogodę (API Open-Meteo).

---

## Struktura projektu

- `app.py` — serwer Flask.
- `requirements.txt` — zależności.
- `Dockerfile` — wieloetapowy build.
- `templates/index.html` — UI.
- `zadanie1.md` — sprawozdanie do moodle.

---

## Jak uruchomić?

### Budowanie obrazu
```bash
docker build -t zadanie1 .
```

### Uruchomienie kontenera
```bash
docker run -d -p 5000:5000 --name zadanie1_container zadanie1
```

### Sprawdzanie logów
```bash
docker logs zadanie1_container
```

### Sprawdzanie warstw i rozmiaru
```bash
docker image inspect zadanie1 --format='{{json .RootFS.Layers}}'
docker image inspect zadanie1 --format='{{.Size}}'
```

---

## Linki

- **GitHub**: [link_do_repozytorium](https://github.com/JakubGoreckii/zadanie1)
- **DockerHub**: [link_do_dockerhub](https://hub.docker.com/r/goras1234/zadanie1)

---

## Zrzut ekranu

(Zrzut ekranu działania aplikacji w przeglądarce)
