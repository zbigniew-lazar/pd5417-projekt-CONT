# pd5417-projekt-CONT

Projekt konteneryzacji analizy jakości danych sekwencyjnych z wykorzystaniem FastQC.

## Zawartość repozytorium

- Dockerfile – obraz Docker zawierający narzędzie FastQC
- docker-compose.yml – konfiguracja usług FastQC i Nginx
- nginx.conf – konfiguracja serwera WWW Nginx
- fastqc_report.png – przykładowy raport wygenerowany przez FastQC

## Cel projektu

Celem projektu było przygotowanie środowiska kontenerowego umożliwiającego automatyczną analizę jakości danych sekwencyjnych zapisanych w pliku FASTQ przy użyciu narzędzia FastQC oraz udostępnienie wyników analizy za pomocą serwera WWW Nginx.

## Uruchomienie

```bash
docker-compose up --build
```

## Wyniki

Po uruchomieniu projektu raport FastQC dostępny jest pod adresem:

http://localhost:8080

Przykładowy wynik analizy został zapisany w pliku:

- fastqc_report.png

## Wykorzystane narzędzia

- Docker
- Docker Compose
- FastQC
- Nginx
- Ubuntu 22.04
