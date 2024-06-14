# Команды Git (Git-Befehle)

## Основные команды (Grundlegende Befehle)

#### 1. **git init**
   - **Инициализирует новый репозиторий Git или переинициализирует существующий репозиторий**
   - Initialisiert ein neues Git-Repository oder reinitialisiert ein bestehendes Repository
   - Пример:
     ```bash
     git init
     ```

#### 2. **git clone**
   - **Клонирует репозиторий в новый каталог**
   - Klont ein Repository in ein neues Verzeichnis
   - Пример:
     ```bash
     git clone https://github.com/user/repo.git
     ```

#### 3. **git add**
   - **Добавляет файлы в индекс (стейджинг)**
   - Fügt Dateien zum Index (Staging) hinzu
   - Пример:
     ```bash
     git add filename
     git add .
     ```

#### 4. **git commit**
   - **Фиксирует изменения с комментарием**
   - Führt einen Commit der Änderungen mit einem Kommentar durch
   - Пример:
     ```bash
     git commit -m "Commit message"
     ```

#### 5. **git status**
   - **Показывает состояние рабочего каталога и индекса**
   - Zeigt den Status des Arbeitsverzeichnisses und des Index an
   - Пример:
     ```bash
     git status
     ```

#### 6. **git push**
   - **Отправляет локальные изменения в удаленный репозиторий**
   - Schiebt lokale Änderungen in das Remote-Repository
   - Пример:
     ```bash
     git push origin branchname
     ```

#### 7. **git pull**
   - **Извлекает изменения из удаленного репозитория и сливает их с локальной веткой**
   - Holt Änderungen aus dem Remote-Repository und merged sie mit dem lokalen Branch
   - Пример:
     ```bash
     git pull origin branchname
     ```

#### 8. **git fetch**
   - **Извлекает изменения из удаленного репозитория, но не сливает их**
   - Holt Änderungen aus dem Remote-Repository, aber merged sie nicht
   - Пример:
     ```bash
     git fetch origin
     ```

#### 9. **git merge**
   - **Сливает одну или несколько веток в текущую ветку**
   - Merged einen oder mehrere Branches in den aktuellen Branch
   - Пример:
     ```bash
     git merge branchname
     ```

#### 10. **git branch**
- **Перечисляет, создает или удаляет ветки**
- Listet Branches auf, erstellt oder löscht sie
- Пример:
```bash
  git branch
  git branch newbranch
  git branch -d branchname
```

#### 11. **git checkout**
- **Переключается на другую ветку или восстанавливает файлы**
- Wechselt zu einem anderen Branch oder stellt Dateien wieder her
- Пример:

```bash
	git checkout branchname
	git checkout -- filename
```

#### 12. **git log**
- **Показывает журнал коммитов для репозитория**
- Zeigt das Commit-Log für das Repository an
- Пример:
  ```bash
  git log
  ```

#### 13. **git reset**
- **Сбрасывает индекс и рабочий каталог к состоянию последнего коммита**
- Setzt den Index und das Arbeitsverzeichnis auf den letzten Commit zurück
- Пример:
  ```bash
  git reset --hard HEAD
  ```

#### 14. **git revert**
- **Создает новый коммит, который отменяет изменения, внесенные в предыдущий коммит**
- Erstellt einen neuen Commit, der die Änderungen des vorherigen Commits rückgängig macht
- Пример:
  ```bash
  git revert commit_hash
  ```

#### 15. **git rebase**
- **Переносит или объединяет набор коммитов на новый базовый коммит**
- Verschiebt oder vereinigt eine Reihe von Commits auf einen neuen Basis-Commit
- Пример:
  ```bash
  git rebase branchname
  ```

#### 16. **git stash**
- **Сохраняет незакоммиченные изменения для восстановления позже**
- Speichert nicht committete Änderungen zur späteren Wiederherstellung
- Пример:
  ```bash
  git stash
  git stash apply
  ```

#### 17. **git tag**
- **Создает тег для указания на конкретный коммит**
- Erstellt ein Tag, um auf einen bestimmten Commit zu verweisen
- Пример:
  ```bash
  git tag v1.0
  git push origin v1.0
  ```

#### 18. **git remote**
- **Управляет подключенными удаленными репозиториями**
- Verwalten der verbundenen Remote-Repositories
- Пример:
  ```bash
  git remote add origin https://github.com/user/repo.git
  git remote -v
  ```

#### 19. **git diff**
- **Показывает различия между коммитами, ветками и рабочими каталогами**
- Zeigt Unterschiede zwischen Commits, Branches und Arbeitsverzeichnissen an
- Пример:
  ```bash
  git diff
  ```


