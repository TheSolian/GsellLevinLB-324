# LB 324

## Aufgabe 2

Erklären Sie hier, wie man `pre-commit` installiert.

Wenn man ein Python Projekt hat, geht das eigentlich ziemlich einfach.

1. Zuerst installiert man das Paket `pre-commit`

```bash
# Windows
pip install pre-commit

# OSX
pip3 install pre-commit
```

2. Danach erstellt man seinen Pre-Commit Hook. Als Beispiel habe ich hier meinen.

```yaml
repos:
  - repo: local
    hooks:
      - id: pytest-check
        stages: [commit]
        types: [python]
        name: pytest-check
        entry: python3 -m pytest
        language: system
        pass_filenames: false
        always_run: true
```

3. Jetzt führt man noch den folgenden Befehl im Terminal/Powershell/CMD aus.

```bash
pre-commit install --hook-type pre-commit --hook-type pre-push
```

Jetzt ist man eigentlich schon einsatzbereit und man kann nun nur Commits machen, wenn alle Tests erfolgreich durchlaufen.

## Aufgabe 4

Erklären Sie hier, wie Sie das Passwort aus Ihrer lokalen `.env` auf Azure übertragen.

Auf Azure kann man in der Konfiguration sogenannte "Application Settins" definieren. Da kann man, wie in einem `.env`, seine geheimen Werte eintragen.


![Azure_env](https://github.com/TheSolian/GsellLevinLB-324/assets/89124854/1b3c913b-c0d6-4c07-a3d9-8a0d2db8af7b)
