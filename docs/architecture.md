# Architecture — Resilience

```mermaid
flowchart TB
 W[Météo] --> ING[Ingestion]
 G[Géospatial] --> ING
 C[Signalements] --> ING
 I[Infrastructures] --> ING
 ING --> R[Risk Engine]
 R --> A[Alert Engine]
 A --> SMS[SMS]
 A --> WEB[Web / Mobile]
 A --> OPS[Centre opérationnel]
 OPS --> FB[Retour terrain]
 FB --> ING
```

## Principes

Sources versionnées, provenance obligatoire, séparation observation/prédiction, seuils d'alerte explicites, résilience des canaux et fonctionnement en faible connectivité.

Les alertes doivent communiquer l'incertitude et éviter de créer une fausse impression de précision.