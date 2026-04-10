# IHSAN — Points à Valider avec les Partenaires

*Pour réunion du 10 Avril 2026*

---

## 1. Questions Stratégiques

### Q1: Quel est le modèle économique visé?

**Options identificadas:**

| Modèle | Description | Avantages | Risques |
|--------|-------------|-----------|---------|
| **B2G** | Licences pour ministère/écoles | Revenus stables, volume | Cycle long, appels d'offres |
| **B2C** | Freemium pour parents | Marché large | Nécessite confiance, marketing |
| **B2B2C** | Partenariat école → accès élèves | Adoption plus facile | Dépendance au partenaire |
| **Hybride** | B2G pour contenu base + B2C pour premium | Diversifié | Complexité |

**Notre recommandation:** **Hybride B2G + B2C**
- B2G: contenu aligné programme national (contrats écoles/wilayas)
- B2C: fonctionnalités premium (analytics détaillés, suivi parent avancé)

**→ Avis demandé:** Quelle est votre expérience avec chaque modèle? Quels sont les contacts existants?

---

### Q2: Quel niveau d'ambition pour le MVP?

**Option A: MVP Minimal** (~3 mois dev)
- Diagnostic initial (1-2 modules)
- Parcours adaptatif basique
- Interface élève functional
- Test avec 1 classe (50-100 élèves)

**Option B: MVP Étendu** (~6 mois dev)
- Diagnostic multi-modules
- Parcours complet avec gamification
- Interfaces élève + parent + expert
- Test avec 3-5 écoles

**Option C: Pilotage Phase** (conception + test)
- Pas de dev maintenant
- Pilotage avec teachers + élèves (3 mois)
- Validation before build

**→ Avis demandé:** Quel niveau d'investissement est acceptable? Quelle timeline pour les partenaires?

---

### Q3: Partenariat Ministère — timing et approche?

**Constat:**
- 2M tablets ENIE distribuées
- Connectivité croissante dans les écoles
- Aucun acteur local dominant sur l'adaptif
- Contexte favorable pour un partenariat

**Options:**

| Timing | Approche | Risques |
|--------|----------|---------|
| **Maintenant** | Contact informal, présentation du concept | Trop tôt? |
| **Après MVP** | Démontrer avec résultats | Perdre temps |
| **En parallèle** | Chercher contacts + build MVP | Risque de misalignment |

**→ Avis demandé:** Avez-vous des contacts au ministère? Quelle est votre stratégie de approche?

---

## 2. Questions Techniques

### Q4: Stack technique — quelle préférence?

**Notre analyse:**

| Stack | Forces | Faiblesses |
|-------|--------|------------|
| **Node.js + TypeScript** | Full-stack JS, communauté large | Moins performant pour algo lourd |
| **Python (FastAPI)** | Excellent pour algo/ML, data processing | 2 codebases (front + back) |
| **Go** | Performant, moderne | Équipe moins familière |
| **Low-code (N8N/Supabase)** | Rapidité,降低成本 | Moins flexible, vendor lock |

**Notre recommandation:** **Python + FastAPI + React/Next.js**
- Python pour le moteur adaptatif (BKT + Bandit)
- Next.js pour le frontend (SSR, i18n native)
- FastAPI pour API propre et dokumentation

**→ Avis demandé:** Quelle est la familiarité de l'équipe avec chaque stack?

---

### Q5: Infrastructure — où héberger?

**Options:**

| Option | Coût estimé | Latency | Contrôle | Risques |
|--------|-------------|---------|----------|---------|
| **Cloud Algeria (CERIST)** | €?? | ✅ Minimale | ✅ Total | Pas de credit cards? |
| **OVHcloud (France)** | ~€50-200/mois | ✅ Bonne (Europe) | ✅ Total | Éloigné |
| **AWS/GCP** | ~$100-500/mois | ⚠️ Variable | ✅ Total | Cher, complexité |
| **Cloudflare** | ~$20-100/mois | ✅ Très bonne | ⚠️ Limité | Vendor lock |

**→ Avis demandé:** Y a-t-il des contraintes légales/réglementaires sur où les données peuvent être stockées?

---

### Q6: Architecture offline-first — priorité absolue?

**Dilemme:**
- Tablets ENIE = connectivité variable
- Offline-first = développement plus complexe + longtemps
- Mais si ça marche pas sur le terrain = échec

**Option alternative:**
- Online-first avec sync периодиque
- Gère le offline via Service Workers progressivement

**→ Avis demandé:** Quelle est la réalité de la connectivité dans les écoles ciblées?

---

## 3. Questions Contenu

### Q7: Par où commencer — quelles matières/niveaux?

**Suggestion:**

| Phase | Matière | Niveaux | Justification |
|-------|---------|---------|---------------|
| **1** | Mathématiques | CP → CE2 | Lacunes les plusdocumentées, structure claire |
| **2** | Arabe (lecture) | CP → CE1 | Phonétique, alphabet — fondation |
| **3** | Français | CE1 → CE2 | Après arabe (transfert possible) |
| **4** | Anglais | CM1 → CM2 | Plus facile à adapter (contenu existant) |

**→ Avis demandé:** Quelle est la priority du partenaire? Y a-t-il des contraintes du ministère sur les matières?

---

### Q8: Comment créer le contenu initial?

**Options:**

| Approche | Coût | Temps | Qualité |
|----------|------|-------|---------|
| **Équipe interne** | Faible (salaires) | Lent (6-12 mois) | Contrôlée |
| **Enseignants Freelance** | Moyen | Moyen (3-6 mois) | Variable |
| **Partenariat éditeurs** | Partage revenus | Rapide | Professionnelle |
| **AI + Curation** | Faible | Rapide | À valider |

**→ Avis demandé:** Y a-t-il des enseignants/experts pédagogique interessés? Des contacts avec des éditeurs?

---

## 4. Questions Budget & Ressources

### Q9: Quel budget pour la Phase 1 (Pilotage + MVP)?

**Estimation très préliminaire:**

| Poste | Coût estimé (6 mois) |
|-------|---------------------|
| Développement (1-2 devs) | €15,000 - €30,000 |
| Infrastructure (dev + prod) | €500 - €1,500 |
| Contenu initial (contrat enseignants) | €5,000 - €15,000 |
| Design/UX | €3,000 - €8,000 |
| Tests & validation | €2,000 - €5,000 |
| **TOTAL** | **€25,000 - €60,000** |

**→ Avis demandé:** Quel est le budget disponible? Quelle est la flexibilité?

---

### Q10: Quelle équipe est nécessaire?

**Ressources minimales:**

| Rôle | Temps | Compétences |
|------|-------|-------------|
| Product Owner | 50% | Vision, priorisation |
| Lead Developer | 80% | Architecture, code |
| Frontend Dev | 80% | React/Next.js |
| Expert Pédagogique | 20% | Contenu, validation |
| Designer UX | 30% | Design system, prototypes |

**→ Avis demandé:** Quelles ressources sont déjà disponibles dans l'équipe? Quels rôles manquent?

---

## 5. Questions Lancement

### Q11: Quel marché pour le pilot?

**Options:**

| Option | Sélection | Avantages | Risques |
|--------|-----------|-----------|---------|
| **1 wilaya** | Tizi-Ouzou ou Alger | Contrôlé, diverse | Limité |
| **3-5 écoles** | Uniquement Alger | Facilement manageable | Pas représentatif |
| **En ligne (B2C)** | Tout Algeria | Large, rapide | Pas de contrôle terrain |
| **Partenariat existant** | Là où partenaires ont contacts |已有关系 | Dépend de tiers |

**→ Avis demandé:** Y a-t-il des écoles ou contacts existants?

---

### Q12: Comment mesurer le succès du pilot?

**KPIs sugerés:**

| Catégorie | KPI | Target suggéré |
|-----------|-----|----------------|
| **Engagement** | Taux d'utilisation weekly | >70% |
| **Learning** | Score improvement après 1 mois | +15% |
| **Retention** | Dévouement quotidien streak | >60% |
| **Satisfaction** | NPS des élèves | >40 |
| **Technical** | Uptime | >99% |

**→ Avis demandé:** Quels metrics sont prioritaires pour les partenaires?

---

## 6. Prochaines Étapes Suggérées

```
SEMAINE 1-2:
├── Valider modèle économique (Q1)
├── Identifier stack technique (Q4)
└── Confirmer budget (Q9)

SEMAINE 3-4:
├── Finaliser team (Q10)
├── Identifier écoles pour pilot (Q11)
└── Commencer contacts ministère (Q3)

MOIS 2:
├── Kickoff développement MVP
├── Recrutement experts pédagogiques
└── Création contenu Phase 1

MOIS 3-4:
├── Tests internes
└── itération based on feedback
```

---

## Annexe: Points à Discuter Plus Tard

Ces questions sont importantes mais peuvent attendre:

1. **RGPD / Protection données:** Consentement parents, données élèves
2. **Accessibilité:** Comment gérer les élèves avec besoins spéciaux?
3. **Évaluation nationale:** Comment IHSAN prépare-t-il aux examens?
4. **Mise à jour contenu:** Qui met à jour quand le программа change?
5. **Monétisation autres:** Publicité? Partenariats marques?
6. **Expansion:** Pourquoi pas d'autres pays arabes/francophones?

---

*Ce document sera mis à jour après la réunion avec les décisions validées.*
