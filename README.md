# System Recenzowania Artykułów Naukowych (Article Peer-Review System)

System REST API do zarządzania procesem recenzowania artykułów naukowych, umożliwiający przeprowadzanie pełnego cyklu - od zgłoszenia artykułu, przez proces recenzji, po decyzję i ewentualne kolejne rundy poprawek.

## Spis treści
- [Funkcjonalności](#funkcjonalności)
- [Architektura systemu](#architektura-systemu)
- [Technologie](#technologie)
- [Struktura bazy danych](#struktura-bazy-danych)
- [API Endpoints](#api-endpoints)
- [Instalacja i uruchomienie](#instalacja-i-uruchomienie)
- [Konfiguracja](#konfiguracja)
- [Testy](#testy)
- [Dokumentacja API](#dokumentacja-api)

## Funkcjonalności

### Zarządzanie artykułami
- Dodawanie nowych artykułów
- Przeglądanie i edycja artykułów
- Przesyłanie pełnych tekstów artykułów
- Śledzenie statusu artykułu w całym procesie recenzji

### Zarządzanie recenzjami
- Przydzielanie recenzentów do artykułów
- Wypełnianie formularzy recenzji
- Dodawanie komentarzy dla autorów i poufnych uwag dla redaktorów
- Ocenianie artykułów według określonych kryteriów

### Podejmowanie decyzji
- Wydawanie decyzji przez redaktorów (akceptacja, minor/major revision, odrzucenie)
- Dostarczanie autorom informacji zwrotnej od redakcji
- Rejestrowanie historii decyzji

### Zarządzanie rundami recenzji
- Obsługa wielu rund recenzji dla jednego artykułu
- Śledzenie odpowiedzi autorów na uwagi recenzentów
- Zarządzanie kolejnymi wersjami artykułu

## Architektura systemu

System został zaprojektowany zgodnie z wzorcem warstwowym:

1. **Warstwa kontrolerów (REST API)** - obsługa żądań HTTP i odpowiedzi
2. **Warstwa serwisów** - logika biznesowa
3. **Warstwa repozytoriów** - dostęp do bazy danych
4. **Warstwa modeli** - encje reprezentujące dane biznesowe

## Technologie

- **Java** - język programowania
- **Spring Boot** - framework do budowy aplikacji
- **Spring Data JPA** - dostęp do bazy danych
- **Hibernate** - ORM (Object-Relational Mapping)
- **MySQL** - system zarządzania bazą danych
- **Maven** - zarządzanie zależnościami
- **Docker** - konteneryzacja
- **JUnit** - framework do testów
- **Flyway** - migracje bazy danych

## Struktura bazy danych

System opiera się na następujących głównych encjach:

- **User** - użytkownicy systemu (autorzy, recenzenci, redaktorzy)
- **Article** - artykuły naukowe
- **Review** - recenzje artykułów
- **RevisionRound** - rundy rewizji artykułu
- **Decision** - decyzje redaktorów

Diagram klas dostępny jest w dokumentacji technicznej.

## API Endpoints

### Artykuły

```
GET    /api/articles - lista wszystkich artykułów
GET    /api/articles/{id} - szczegóły pojedynczego artykułu
POST   /api/articles - dodanie nowego artykułu
PUT    /api/articles/{id} - aktualizacja artykułu
DELETE /api/articles/{id} - usunięcie artykułu
GET    /api/articles/{id}/reviews - lista recenzji dla artykułu
GET    /api/articles/{id}/revisions - lista rund rewizji dla artykułu
```

### Użytkownicy

```
GET    /api/users - lista wszystkich użytkowników
GET    /
