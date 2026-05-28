# KEOH-Modifications-Log

Stand: 2026-05-28 · Fork von [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)

## Übersicht

Dieser Fork erweitert das Original-Tool um DACH-spezifische Design-Patterns, KEOH-Editorial-Branding und einen MCP-Server-Layer für Multi-Client-Distribution. Die Kern-Engine bleibt unverändert. Erweiterungen sind in `src/ui-ux-pro-max/data/keoh-extensions/` und (geplant) in `mcp-server/` abgelegt.

## Änderungen Stand 28.05.2026

### 1. LICENSE
- Original MIT-Lizenz beibehalten
- Zweite Copyright-Zeile für KEOH-Modifikationen hinzugefügt

### 2. README
- Attribution-Header vor Original-README
- Hinweis auf Erweiterungen
- Link zurück zum Original

### 3. Neue Color-Palette
Datei: `src/ui-ux-pro-max/data/keoh-extensions/keoh-editorial-palette.csv`
- KEOH Editorial · Cream-Rust-Gold aus Styleguide 2 Hell
- KEOH Editorial Soft · weichere Variante für Wellness und Healthcare

## Geplante Erweiterungen (Roadmap)

### 4. MCP-Server-Layer (stdio Transport)

**Was:** Lokaler MCP-Server-Wrapper für die Reasoning-Engine. Macht den Skill in allen MCP-fähigen AI-Clients nutzbar (Cursor, Windsurf, Claude Desktop, ChatGPT-Apps), nicht nur in Claude Code.

**Wie:** TypeScript-basierter stdio-MCP-Server. Wrapped die bestehenden CSVs plus Reasoning-Logik in MCP-Tools. Kein HTTP-Server, kein Hosting nötig.

**Pfad:** `mcp-server/server.ts` plus npm-bin-Entry für globale Installation.

**Installation für End-User:**
```bash
npm install -g keoh-design-mcp
```
Plus Config-Update in `claude_desktop_config.json` oder MCP-Config des jeweiligen Clients.

**Vorteile:**
- Multi-Client-Distribution aus einer Codebasis (Cursor, Windsurf, Desktop, etc.)
- 100 Prozent lokal, keine Daten verlassen den Computer
- DSGVO-konform per Design
- Differenzierung vom Original (Original hat keinen MCP-Layer)
- Cloudflare-Workers-kompatibel für spätere Remote-Variante

### 5. DACH-Compliance-Reasoning-Rules
- DSGVO-Cookie-Banner-Patterns
- EU-AI-Act-Anwendung in Hiring-Tools und Recruiter-UIs
- BFSG (Barrierefreiheitsstärkungsgesetz) Patterns ab Juni 2025
- Impressum-Layout-Empfehlungen für DACH-Brands

### 6. Customer-Success-Onboarding-Patterns
- Welcome-Screen-Reasoning für SaaS
- Feature-Tour-Sequenzen
- Aktivierungs-Moment-Identifikation
- Drop-off-Prevention-Patterns

### 7. Cloudflare-Workers-Tech-Stack-Guidelines
- Edge-Compute-UI-Patterns
- KV-Storage-Integration-UX
- Workers-Specific-Performance-Hinweise
- Plus später: Remote-MCP-Variante via Cloudflare Workers

## Beitrag zurück ans Original

Wenn KEOH-Erweiterungen für die breite Community sinnvoll sind, werden sie als Pull-Request an das Original-Repo eingereicht. Der MCP-Server-Layer wäre ein starker Kandidat für Upstream-Beitrag, weil er das Original-Tool für eine viel breitere Plattform-Reichweite öffnet.

## Lizenz

MIT (siehe LICENSE-Datei).
