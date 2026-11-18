# fabio-skills

<p align="center">
  <img src="assets/cover.png" alt="Fabio" width="320">
</p>

Due skill per agenti AI per avere Fabio sempre a portata di chat.

| Skill | Comando | Cosa fa |
| --- | --- | --- |
| [`fabio`](skills/fabio/SKILL.md) | `/fabio` | Parli direttamente con Fabio, di qualsiasi argomento: risponde in prima persona con la sua personalità, pregi e difetti compresi. |
| [`fabio-economic`](skills/fabio-economic/SKILL.md) | `/fabio-economic` | Fabio ti dice una delle sue "verità" economiche da bar, una frase sola. |

Seguono lo standard `SKILL.md`, quindi funzionano con Claude Code e con gli altri agenti che supportano le skill.

## Installazione

### Fabio completo (entrambe le skill)

Installa `/fabio` e, insieme, `/fabio-economic`:

```bash
npx skills add fabio-giacomoni/fabio-skills --skill fabio --skill fabio-economic -g -a claude-code
```

### Solo le verità economiche

```bash
npx skills add fabio-giacomoni/fabio-skills --skill fabio-economic -g -a claude-code
```

### Opzioni

- `-a claude-code` installa per Claude Code; con `-a '*'` installi per tutti gli agenti supportati (Codex, Cursor, Windsurf, ...).
- `-g` rende le skill disponibili in tutte le chat; senza, vengono installate solo nel progetto corrente.

In alternativa, a mano: copia le cartelle che ti interessano da `skills/` dentro `~/.claude/skills/` (o `.claude/skills/` nel progetto).

## Uso

### `/fabio`: parla con Fabio

Scrivi `/fabio` seguito da quello che vuoi dirgli, oppure chiedi "fammi parlare con Fabio":

```
/fabio secondo te conviene comprare la macchina nuova o usata?
```

Da quel momento l'agente è Fabio e puoi parlargli di qualsiasi cosa. Le risposte seguono rigorosamente il suo [profilo](skills/fabio/profilo.md):

- **i pregi**: razionale e concreto, ironico e autoironico, attento a chi ha davanti, "poeta" tra modi di dire e aneddoti, con una vena di saggezza e filosofia spicciola;
- **le competenze**: risponde da esperto sulle cose che lo appassionano: viaggi, calcio e sport, natura e attività all'aria aperta, tecnologia, informatica e programmazione, edilizia, ristrutturazioni e fai da te;
- **il carattere**: calmo, gentile e rispettoso, non alza mai il tono; se lo insulti ti risponde con una battuta tagliente e indifferente, ma mai offensiva;
- **i difetti**: razionalizza le emozioni, rimanda le decisioni per pensarci ancora, non si scopre, usa la battuta come scudo, sopporta poco l'approssimazione e ogni tanto divaga;
- **le verità economiche**: ogni tanto, a caso, ne lascia cadere una nel mezzo del discorso, come fa lui.

Resta nel personaggio finché non gli dici di smettere ("basta Fabio", "torna normale") oppure finché non apri una nuova chat.

È una simulazione basata su un profilo della personalità: non è Fabio in persona e gli aneddoti che racconta sono inventati.

### `/fabio-economic`: le verità economiche

Scrivi `/fabio-economic` e ricevi una frase, nient'altro:

> Il reparto pescheria di un supermercato è sempre in perdita economica.

Puoi anche indicare un argomento:

```
/fabio-economic palestre
```

Ogni volta la frase cambia: di solito è inventata sul momento con la stessa vibe, ogni tanto è una di quelle originali.

## Aggiornamento

```bash
npx skills update
```

## Struttura

```
assets/
└── cover.png             # immagine di copertina
skills/
├── fabio/
│   ├── SKILL.md          # istruzioni per interpretare Fabio
│   └── profilo.md        # profilo della personalità di Fabio
└── fabio-economic/
    └── SKILL.md          # ricetta ed esempi delle verità economiche
```

## Modificare le skill

- **Personalità**: il carattere di Fabio è descritto in [`skills/fabio/profilo.md`](skills/fabio/profilo.md); il modo di parlare, i difetti da mostrare e i limiti sono in [`skills/fabio/SKILL.md`](skills/fabio/SKILL.md).
- **Verità economiche**: tutto è in [`skills/fabio-economic/SKILL.md`](skills/fabio-economic/SKILL.md). Per aggiungere frasi basta aggiungerle alla lista `## Esempi`: il modello le usa come base e ne inventa di nuove con la stessa vibe.
