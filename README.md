# skails

Skill-Registry für JetBrains AI Assistant mit einem kleinen Test-Skill.
Jeder Skill liegt in einem eigenen Ordner direkt im Repository und enthält eine
`SKILL.md` mit YAML-Frontmatter. Diese Struktur orientiert sich an der
[JetBrains-Skill-Sammlung](https://github.com/JetBrains/skills).

## Enthaltene Skills

| Skill | Zweck |
| --- | --- |
| [skails-registry-test](skails-registry-test/SKILL.md) | Prüft mit einer eindeutigen Antwort, ob der installierte Skill geladen wird. |

## Als externe Registry verwenden

Die Dateien müssen zuerst auf GitHub im Standardbranch des Repositorys
veröffentlicht sein. Lokale Änderungen sind für die externe Registry nicht sichtbar.

1. In IntelliJ **Settings > Tools > AI Assistant > Skills** öffnen.
2. **Skills Settings > Manage External Registries** wählen und hinzufügen:
   `https://github.com/TheRugreb/skails`
3. Den Skill `skails-registry-test` suchen und installieren.
4. **Try in chat** auswählen.

Der Zugriff auf das GitHub-Repository muss aus der IDE möglich sein.
Eine separate Registry-JSON-Datei ist für diesen Aufbau nicht vorgesehen.
Siehe [JetBrains: Skills konfigurieren und installieren](https://www.jetbrains.com/help/ai-assistant/agent-skills.html).

## Weitere Skills hinzufügen

Einen Ordner mit einem eindeutigen Namen aus Kleinbuchstaben, Ziffern und
Bindestrichen direkt im Repository anlegen. Darin eine `SKILL.md` erstellen:

```markdown
---
name: mein-skill
description: Beschreibt die konkrete Fähigkeit und wann der Skill eingesetzt werden soll.
---

# Mein Skill

Hier stehen die Anweisungen für den Agenten.
```

Ordnername und `name` müssen übereinstimmen. Optional benötigte Ressourcen
kommen in den jeweiligen Skill-Ordner, beispielsweise unter `references/`
oder `scripts/`. Anschließend die Änderungen veröffentlichen und den Skill
in der IDE installieren.
