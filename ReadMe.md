# MySQL Docker Compose Setup and CRUD Operations

Diese Anleitung beschreibt, wie du MySQL mit Docker Compose einrichtest und grundlegende CRUD-Operationen (Create, Read, Update, Delete) durchführst.

## Voraussetzungen

- Docker und Docker Compose müssen auf deinem System installiert sein. Du kannst Docker von der offiziellen Docker-Website herunterladen und installieren.

## Verbindung zur MySQL-Datenbank herstellen

### Docker-Container starten
```bash
docker-compose up -d  
```
### Docker-Container überprüfen

Überprüfe, ob der MySQL-Container läuft:

```bash
docker ps
```

## Mit dem MySQL-Container verbinden
### Verwende den folgenden Befehl, um eine MySQL-Shell innerhalb des Containers zu öffnen:
```bash
docker exec -it mysql-container mysql -u demo_user -p 
```
Gib das Passwort demo_password ein, wenn du dazu aufgefordert wirst.

## Datenbank auswählen
### Bevor du CRUD-Operationen durchführst, stelle sicher, dass du die Datenbank auswählst:
```bash
USE demo_db;
```

## CRUD-Operationen durchführen
### Tabelle erstellen

```bash
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50),
    email VARCHAR(50)
);
```
## Daten einfügen (Create)
```bash
INSERT INTO users (username, email) VALUES ('kim_fluekiger', 'kim@kimfluekiger.ch');
```

## Daten lesen (Read)
```bash
SELECT * FROM users;
```
## Daten aktualisieren (Update)
```bash
UPDATE users SET email = 'info@kimfluekiger.ch' WHERE username = 'kim_fluekiger';
```
## Daten löschen (Delete)
```bash
DELETE FROM users WHERE username = 'kim_fluekiger';

```
