# IHSAN — منصة إحسان للتعلم التكيفي
## Rapport d'Avancement — 10 Avril 2026

---

## 1. Résumé Exécutif

**IHSAN** est une plateforme d'apprentissage adaptatif conçue spécifiquement pour les élèves du primaire algérien (6-11 ans). Elle détecte précocement les lacunes pédagogiques et propose un parcours de remédiation sur mesure, sans intervention directe continue d'enseignants.

**Stade actuel:** Design & Prototypage — Phase 2/4

| Phase | Status | Date cible |
|-------|--------|------------|
| 1. Vision & Conception | ✅ Terminé | Janvier 2026 |
| 2. Design & Prototypage | 🚧 En cours | Avril 2026 |
| 3. Développement MVP | ⏳ Planifié | Juin 2026 |
| 4. Tests & Lancement | ⏳ Planifié | Septembre 2026 |

---

## 2. Ce qui a été réalisé

### 2.1 Recherche & Analyse (✅ Terminé)
- **Analyse concurrentielle** de 16 plateformes mondiales (ALEKS, IXL, Khan Academy, DreamBox, etc.)
- **Étude des algorithmes adaptatifs:** BKT, Bandit Multi-Bras, Deep RL
- **Benchmarks technologiques:** Stack technique, architecture, performance
- **Étude du contexte algérien:** Programme national, infrastructure ENIE, contexte culturel

### 2.2 Identité de Marque (✅ Terminé)
| Élément | Décision |
|---------|----------|
| **Nom** | IHSAN (إحسان) — Excellence, benevolence in Arabic/Islamic tradition |
| **Positionnement** | Système expert d'apprentissage adaptatif pour le primaire algérien |
| **Persona** | Tutor intelligent, émotionnellement sûr, ancré dans l'identité algérienne |

### 2.3 Design System — "The Digital Majlis" (✅ Terminé)

**Principes créatifs:**
- RTL-first (droite vers gauche)
- "Digital Majlis" — espace de sanctuaire pour l'apprentissage
- Asymétrie intentionnelle plutôt que grilles rigides
- Zéro bordure — utiliser les tons pour séparer les sections

**Palette de couleurs:**
| Rôle | Couleur | Usage |
|------|---------|-------|
| Primary | `#00535b` (Turquoise profond) | Actions principales, marque |
| Secondary | `#8c4e35` (Ochre/Sepia) | Achievements, "Aha!" moments |
| Background | `#faf9f6` (Sable crémeux) | Canvas de base |
| Success | Mint green | États de réussite |
| Review | Amber doux | États à réviser |
| Error | Rose doux | États d'erreur (pas de rouge agressif) |

**Typographie:**
- Arabe: Tajawal / Cairo (titres + corps)
- Nombres/Systèmes: Inter (précision technique)
- Échelle: Display MD → Body SM (tension dynamique)

**Composants clés:**
- Boutons avec gradients souples Primary → Primary Container
- Chips de progression (soft, rounded stones)
- "Focus Veil" — mode concentration masquant le reste
- Cards sans bordures, séparées par espacement vertical

### 2.4 Architecture Utilisateurs (✅ Définie)

```
┌─────────────────────────────────────────────────────────────┐
│                    PLATEFORME IHSAN                          │
├──────────────┬──────────────────┬───────────────────────────┤
│   ÉLÈVES     │     PARENTS      │      EXPERTS              │
│  (6-11 ans)  │  (Mobile-first)  │   (Back-office)           │
├──────────────┼──────────────────┼───────────────────────────┤
│ • Diagnostic │ • Suivi清楚     │ • Création contenu        │
│ • Parcours   │ • Rapports       │ • Monitoring global       │
│ • Gamification│ • Communication │ • Gestion curriculum      │
│ • Assistance │                  │                           │
└──────────────┴──────────────────┴───────────────────────────┘
```

### 2.5 Mockups & Prototypes (✅ Générés)

| Prototype | Status | Description |
|-----------|--------|-------------|
| **Expert Dashboard** | ✅ HTML | Vue analytique pour experts pédagogiques |
| **Student Interface** | ✅ DESIGN.md | Design system complet students |
| **Parent Dashboard** | ⏳ À faire | Design en cours |

---

## 3. Décisions Techniques Clés

### 3.1 Algorithme Adaptatif
**Choix:** Hybridation BKT + Bandit Multi-Bras

| Composant | Rôle |
|-----------|------|
| **BKT (Bayesian Knowledge Tracing)** | Suivi de maîtrise par compétence (fondation éprouvée) |
| **Bandit Multi-Bras** | Optimisation du parcours d'exercices (modèle EvidenceB) |

**Justification:** BKT offre une base solide pour le diagnostic, tandis que le bandit multi-bras optimise continuellement l'expérience. Cette combinaison est inspirée du modèle EvidenceB/Adaptiv'Math (France, P2IA).

### 3.2 Architecture Technique
- **Offline-first** pour les tablettes ENIE
- **RTL-native** (pas juste RTL CSS — architecture pensée RTL)
- **Touch-optimized:** 44px minimum, 60px pour CP-CE1
- **Performance:** Low-spec Android (1GB RAM, Cortex-A7)

### 3.3 Contenu & IA Générative
- Contenu aligné sur le programme national algérien
- IA générative pour accélérer la création de contenu Arabic
- Curation humaine par des enseignants algériens

---

## 4. Ce qui reste à faire

### Phase 3: Développement MVP (Planifié — Avril à Juin 2026)
- [ ] Backend: API + Database + Auth
- [ ] Module diagnostic initial
- [ ] Parcours adaptatif (BKT + bandit)
- [ ] Interface Élève responsive
- [ ] Interface Expert (CMS)
- [ ] Intégration contenu pédagogique

### Phase 4: Tests & Lancement (Planifié — Juin à Septembre 2026)
- [ ] Tests utilisateurs (élèves réels)
- [ ] Tests performance sur tablets ENIE
- [ ] Beta-test avec écoles partenaires
- [ ] Lancement officiel

---

## 5. Points à valider avec les partenaires

> (Voir document séparé: 03-Points-a-Valider.md)

---

## 6. Risques identifiés

| Risque | Impact | Mitigation |
|--------|--------|------------|
| **Tablettes ENIE** — performance limitée | Élevé | Tests réguliers sur hardware réel |
| **Contenu Arabic** — pénurie de material numérique | Moyen | Partenariats avec éditeurs locaux |
| ** Adoption parents** — fracture numérique | Moyen | Interface mobile-first, guide d'utilisation |
| **Validation Pédagogique** — alignement programme national | Élevé | Implication d'experts dès Phase 2 |

---

## 7. Ressources & Équipe actuelle

- **Équipe:** 1 porteur de projet + partenaires
- **Budget:** En discussion
- **Infrastructure:** Cloud (à définir)

---

*Document généré le 10 Avril 2026 pour la réunion partenaires*
