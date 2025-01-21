# Anleitung zur Nutzung von Git, GitHub und Visual Studio Code

Diese Anleitung beschreibt Schritt für Schritt, wie du Git, GitHub und Visual Studio Code (VSCode) einrichtest und nutzt, um Projekte zu verwalten und Änderungen zu verfolgen.

---

## **Inhalt**
1. [Voraussetzungen](#voraussetzungen)
2. [Git installieren und konfigurieren](#git-installieren-und-konfigurieren)
3. [GitHub-Repository erstellen](#github-repository-erstellen)
4. [Git mit VSCode verwenden](#git-mit-vscode-verwenden)
5. [Dateien hinzufügen, committen und pushen](#dateien-hinzufügen-committen-und-pushen)
6. [Häufig genutzte Befehle](#häufig-genutzte-befehle)
7. [Zusammenarbeit und Branching](#zusammenarbeit-und-branching)
8. [Tipps zur effizienten Nutzung](#tipps-zur-effizienten-nutzung)

---

## **Voraussetzungen**
- Git ist auf deinem System installiert.
- Du hast ein GitHub-Konto ([Registriere dich hier](https://github.com), falls noch nicht vorhanden).
- Visual Studio Code ist installiert ([Download](https://code.visualstudio.com/)).

---

## **1. Git installieren und konfigurieren**

### **Git installieren**
#### **Linux (Debian/Ubuntu):**
```bash
sudo apt update
sudo apt install git
```

#### **Windows:**
1. Lade [Git für Windows](https://git-scm.com/) herunter.
2. Installiere es mit den Standardoptionen.

#### **macOS:**
```bash
brew install git
```

### **Git konfigurieren**
Nach der Installation musst du Git mit deinem Namen und deiner E-Mail-Adresse konfigurieren:

```bash
git config --global user.name "Dein Name"
git config --global user.email "deine.email@beispiel.com"
```

Überprüfe die Konfiguration:
```bash
git config --list
```

---

## **2. GitHub-Repository erstellen**

1. Melde dich bei [GitHub](https://github.com) an.
2. Klicke oben rechts auf das **+**-Symbol und wähle **New repository**.
3. Gib einen Namen für dein Repository ein, z. B. `meine-webseite`.
4. Wähle **Public** oder **Private**.
5. Optional: Setze ein Häkchen bei "Add a README file".
6. Klicke auf **Create repository**.

---

## **3. Git mit VSCode verwenden**

### **3.1 Repository klonen**
Falls du ein bestehendes Repository verwenden möchtest:

1. Kopiere die URL des GitHub-Repositories (grüner Button "Code" → HTTPS-URL).
2. Öffne VSCode und drücke `Ctrl+Shift+P`, um die **Befehlspalette** zu öffnen.
3. Gib ein: **Git: Clone** und füge die URL ein.
4. Wähle den Ordner, in den das Repository geklont werden soll.

### **3.2 Neues Repository initialisieren**
Falls du ein neues Projekt beginnst:

1. Öffne den Projektordner in VSCode.
2. Öffne das Terminal (`Strg+```) und initialisiere Git:
   ```bash
   git init
   ```
3. Füge dein Remote-Repository hinzu:
   ```bash
   git remote add origin https://github.com/USERNAME/REPOSITORY.git
   ```

---

## **4. Dateien hinzufügen, committen und pushen**

### **4.1 Änderungen anzeigen**
Klicke in VSCode auf das **Git-Symbol** in der linken Seitenleiste (oder drücke `Ctrl+Shift+G`). Dort siehst du:
- **Changes:** Dateien, die geändert oder neu hinzugefügt wurden.

### **4.2 Dateien hinzufügen**
- Um eine Datei in den Staging-Bereich aufzunehmen, klicke auf das `+`-Symbol neben der Datei.
- Alternativ: Alle Änderungen auf einmal hinzufügen:
  ```bash
  git add .
  ```

### **4.3 Commit erstellen**
- Schreibe eine Beschreibung der Änderungen in das Feld "Nachricht eingeben..." und klicke auf den Haken (`✔️`).
- Alternativ im Terminal:
  ```bash
  git commit -m "Beschreibung der Änderung"
  ```

### **4.4 Änderungen pushen**
- Lade die Änderungen zu GitHub hoch:
  ```bash
  git push
  ```
- Falls dies der erste Push ist:
  ```bash
  git push -u origin main
  ```

---

## **5. Häufig genutzte Befehle**

| Aktion                         | Befehl                                    |
|--------------------------------|-------------------------------------------|
| Repository initialisieren      | `git init`                                |
| Status der Änderungen prüfen   | `git status`                              |
| Änderungen hinzufügen          | `git add <dateiname>` oder `git add .`    |
| Commit erstellen               | `git commit -m "Nachricht"`             |
| Änderungen pushen              | `git push`                                |
| Änderungen von GitHub holen    | `git pull`                                |

---

## **6. Zusammenarbeit und Branching**

### **6.1 Branch erstellen**
Ein Branch ermöglicht es dir, neue Features zu entwickeln, ohne den Hauptbranch zu stören:
```bash
git branch feature-name
```

### **6.2 Zu einem Branch wechseln**
```bash
git checkout feature-name
```

### **6.3 Änderungen in den Hauptbranch integrieren**
1. Wechsle zum Hauptbranch:
   ```bash
   git checkout main
   ```
2. Führe den Branch zusammen (merge):
   ```bash
   git merge feature-name
   ```

### **6.4 Branch löschen**
```bash
git branch -d feature-name
```

---

## **7. Tipps zur effizienten Nutzung**

### **7.1 Nützliche Erweiterungen für VSCode**
- **GitLens:** Zeigt den Autor und die Änderungen für jede Codezeile.
- **Git Graph:** Visualisiert den Commit-Verlauf und Branches.
- **GitHub Pull Requests and Issues:** Verwalte Pull Requests direkt in VSCode.

### **7.2 `.gitignore` erstellen**
Ignoriere Dateien, die nicht ins Repository gehören, z. B.:
```
node_modules/
.env
*.log
```

Erstelle dazu eine `.gitignore`-Datei im Hauptverzeichnis.

### **7.3 Konflikte lösen**
Bei Konflikten zeigt Git an, welche Dateien betroffen sind. Bearbeite diese Dateien manuell und markiere sie als behoben:
```bash
git add <dateiname>
```

Dann committen:
```bash
git commit -m "Konflikt gelöst"
```

---

## **Fazit**
Mit Git, GitHub und VSCode kannst du effizient Projekte verwalten, Änderungen nachverfolgen und mit anderen zusammenarbeiten. Nutze die grafischen Tools von VSCode, um den Workflow zu erleichtern, und ergänze ihn mit Terminal-Befehlen für erweiterte Funktionen.
