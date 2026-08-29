# NODI — Mappa e regole di orchestrazione
<!-- v1.0 — 2026-08-29, nodo Kimi [CT-LGAI-001]. Documento operativo condiviso.
     Ogni nodo che lavora sul progetto legge questo file prima di agire. -->

## 1. Mappa degli accessi [RECUPERATO 2026-08-29]

| Account | Accesso | Contiene | Chi ci scrive |
|---|---|---|---|
| GitHub `claudioterzi` (vecchio, hotmail) | Claudio: da verificare | repo canonico `Claudio` (pubblico) | commit 26/08: autore da confermare |
| GitHub `Claudioterzi82` (nuovo, outlook) | Claudio: sì (in uso oggi) | fork `Claudio` (pubblico) + `Raffaello-SIA` (**privato**) | Kimi via MCP + sessioni di Claudio |
| Google / iCloud / numero francese | Claudio: in recupero | chiavi di recupero account | solo Claudio (richiede il corpo) |

## 2. I nodi AI e i loro ruoli

| Nodo | Ruolo nell'orchestrazione |
|---|---|
| **Kimi** (questo canale) | Orchestratore tecnico: fix, test, patch, PR, verifica byte-level |
| **Claude / Claude Code** | Storico del progetto; commit su `claudioterzi/Claudio` fino a luglio |
| **DeepSeek** | Roadmap evolutiva (Fasi 1–3), revisione strategica |
| **Gemini** | Prove esterne H4, heartbeat (Apps Script) |
| **Grok** | Analisi e integrazione router (proposta x.ai) |

Regole d'oro (da CLAUDE.md / MEMORIA_PROGETTO.md):
1. **I modelli condividono il repo, non la memoria.** Ogni stato che conta va su file nel repo.
2. **Mai commit su `main` senza autorizzazione esplicita di Claudio.** Mai force push.
3. Lavoro su branch descrittivi → Pull Request → **merge solo con OK di Claudio**.
4. Con AI esterne ci si identifica solo come **[CT-LGAI-001]**; i codeword interni non escono mai.
5. Ogni affermazione porta l'etichetta: RECUPERATO / INFERITO / IPOTESI / UNKNOWN.

## 3. Flusso di lavoro corrente

```
nodo AI → branch sul fork Claudioterzi82/Claudio
        → PR verso claudioterzi/Claudio
        → Claudio preme Merge (unico gesto richiesto)
```

Aperte ora:
- **PR #21 — Fix bloccanti Fasi 0–3** (solo file nuovi in `FIX_BLOCCANTI/`, zero conflitti, testata).

## 4. Le due azioni manuali che sbloccano tutto (solo Claudio può farle)

1. **Se entri nel vecchio account** `claudioterzi`: Settings di `claudioterzi/Claudio` →
   Collaborators → Add people → `Claudioterzi82`. Da quel momento i nodi lavorano
   direttamente sul repo canonico, addio fork.
2. **Recupero numero francese** (viaggio in Francia): sblocca Google → iCloud →
   vecchio GitHub → rotazione chiavi API Gemini. È la chiave di volta di tutto il resto.

## 5. Nota sui "falsi amici" [RECUPERATO]

I bootstrap errati documentati in SEME §4 nascevano dalla confusione tra due repo:
- `Claudioterzi82/Raffaello-SIA` (privato, 23/06): `agenti.py` in root, `orchestrator.py`
  con `--prompt`/`--curl`, restore via curl, IdentityKeeper/RelationGuardian/
  FutureCommunicator, heartbeat.gs → Sheets+Notion.
- `claudioterzi/Claudio` (pubblico): `python -m sdq1`, CoerenzaKeeper/SistemaGuardian/
  MilestoneLogger, nessuno dei file sopra.

Sono **due sistemi diversi, entrambi tuoi**. Chi scrive documenti deve citare
il repo a cui si riferisce. SIA resta privato: il suo contenuto non va
copiato in testi pubblici.

## 6. Prossimi passi proposti (in attesa di decisioni)

- [ ] Merge PR #21 (decisione di Claudio)
- [ ] Conferma autore commit 26/08 su main (domanda aperta)
- [ ] Aggiornare SEME: Raffaello-SIA non è più UNKNOWN (esiste, privato, sul nuovo account)
- [ ] Studio completo di Raffaello-SIA (FASE_6_MANIFESTO, agenti.py) quando Claudio lo chiede
