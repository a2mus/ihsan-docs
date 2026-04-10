# IHSAN — Décisions Clés Validées

*Document pour réunion partenaires — 10 Avril 2026*

---

## 1. Identité & Positionnement

### ✅ Decision 1.1: Nom de la plateforme
**Décision:** IHSAN (إحسان)

**Arguments:**
- IHSAN signifie "excellence" et "bienveillance" en arabe/islamique
- Concept universel mais profondément ancré dans la culture algérienne
- Zakat al-Ilm (l'aumône du savoir) — la plateforme comme acte de bienfaisance éducative
- Mémorable, prononçable dans les 3 langues (arabe, français, anglais)

**Alternatives considérées:**
- "EduAdapt" — trop générique, pas d'identité culturelle
- "Taalim" — trop commun, pas distinctif
- "Noor" — trop lumineux/vague

---

### ✅ Decision 1.2: Cible primaire
**Décision:** Élèves du primaire algérien (6-11 ans, CP → 5AP)

**Arguments:**
- Période critique pour la détection des lacunes (fondations)
- Programme national structuré (4 niveaux)
- Contexte: 2M tablets ENIE distribuées, connectivité croissante
- Lacunes documentées: 61.1% "low performing" (PISA 2015)

**Justification marché:**
- Aucun acteur local dominant sur le segment adaptatif primaire
- Opportunité de partenariat gouvernemental (ministère de l'Éducation)

---

## 2. Design & Expérience Utilisateur

### ✅ Decision 2.1: Design System "The Digital Majlis"
**Décision:** Approach "Digital Majlis" — sanctuaire d'apprentissage

**Principes clés:**
1. **RTL-first structurel** — pas juste CSS, architecture pensée arabo-centrique
2. **Asymétrie intentionnelle** — pas de grilles steriles
3. **Zéro bordure** — tonalités pour séparer (surface-container)
4. **Blancheur émotionelle** — zero FAIL, "learning opportunities"

**Arguments:**
- "Majlis" = espace de reunion/Apprentissage dans la culture algérienne/maghrebine
- Réduit la charge cognitive
- Crée un sentiment de sécurité émotionnelle
- Distinction forte vs. EdTech occidental

**Sources d'inspiration:**
- Architecture traditionnelle maghrebine (cours intérieure, lumière tamisée)
- KDE/GNOME pour l'interface
- Pas de借鉴 directe de Khan Academy (trop occidental)

---

### ✅ Decision 2.2: Palette de couleurs
**Décision:**
| Rôle | Hex | Justification |
|------|-----|---------------|
| Primary | `#00535b` | Turquoise profond — confiance, autorité douce |
| Secondary | `#8c4e35` | Ochre — terre, authenticité algérienne |
| Background | `#faf9f6` | Sable crémeux — warm, easy on eyes |
| Success | Mint | Réussite sans agressivité |
| Review | Amber doux | Attention sans stress |
| Error | Rose doux | Erreur = apprentissage, pas punition |

**Pourquoi pas le rouge standard:**
- Élèves de 6-11 ans — impact émotionnel fort
- Éviter la honte/avoidance de l'erreur
- "Let's try a different way" > "Wrong answer"

---

### ✅ Decision 2.3: Typographie
**Décision:**
- **Arabe:** Tajawal / Cairo — haute lisibilité, élégance moderne
- **Latin/Nombres:** Inter — précision technique, balance moderne
- **Pas de:** Noto Naskh Arabic (trop formel), Arial (generic)

**Justification:**
- Cairo/Tajawal: design moderne Arabic, optimisé pour écrans
- Inter: reconnus pour leur lisibilité sur tous les devices
- Dual-font system: preserve cultural identity + technical clarity

---

### ✅ Decision 2.4: Gamification — 3 piliers
**Décision:**
1. **Streaks quotidiens** (Duolingo-style)
   - 7 jours consécutifs = 3.6x plus de chances de rester
   - "Streak Freeze" optionnel
2. **Sessions courtes (15 min)** + monde virtuel post-session
   - Modèle Smartick: monde accessible après travail
   - Résultats: 50% clients actifs en plus, churn 12% → 5%
3. **Mascottes culturellement algériennes**
   - Un personnage par matière
   - Diversité algérienne (régions, langues)

**Pourquoi pas Classcraft/Prodigy RPG:**
- Trop complexe pour Phase 1
- Risque de distraction vs. apprentissage
- Budget de développement raisonné

---

## 3. Architecture Technique

### ✅ Decision 3.1: Algorithme adaptatif — Hybridation BKT + Bandit Multi-Bras

**Décision:**
```
Parcours Adaptatif = BKT (diagnostic) + Bandit Multi-Bras (optimisation)
```

**Composante BKT:**
- Bayesian Knowledge Tracing
- États binaires: maîtrisé / non maîtrisé par compétence
- Mise à jour probabiliste à chaque interaction
- Inspiration: Mindspark, MATHia

**Composante Bandit Multi-Bras:**
- Apprentissage par renforcement
- Équilibre exploration (nouveaux exercices) vs exploitation (exercices efficaces)
- 8,000+ exercices auto-correctifs
- Inspiration: EvidenceB/Adaptiv'Math (France, P2IA)

**Pourquoi pas DRL (Deep Reinforcement Learning):**
- Trop data-hungry pour Phase 1
- BKT + Bandit = performant + interpretable
- Transition vers DRL possible later (après积累 de données)

---

### ✅ Decision 3.2: Architecture Device — Offline-First
**Décision:** Priorité tablets ENIE (Android, low-spec)

**Contraintes ciblées:**
- 1GB RAM (Cortex-A7)
- Connectivité variable
- Écranssmall (7-10 pouces)

**Implications:**
- PWA avec Service Workers (cache local)
- Contenu downloadable
- Sync quand connexion disponible
- Pas de features heavy (video streaming, etc.)

**Alternative écartée:**
- Web-only (trop lent sans connexion)
- Native app (developpement iOS/Android séparé)

---

### ✅ Decision 3.3: RTL-Native (pas RTL-CSS)
**Décision:** Architecture pensée RTL dès le départ

**Pourquoi:**
- Google Material Design 3 = RTL ready
- Les icônes directionnelles doivent être mirrored
- Les layouts doivent "flow" de droite à gauche
- Éviter les bidouillages CSS later

**Conséquences:**
- Design system avec "RTL-first" flag
- Composants testés en RTL
- Contenu Arabic en priority

---

### ✅ Decision 3.4: Touch-Optimized
**Décision:**
- 44px minimum touch targets (standard)
- **60px pour CP-CE1** (petits doigts, erreurs de tap)
- Espacement généreux entre éléments
- No hover-dependent features

---

## 4. Modèle Pédagogique

### ✅ Decision 4.1: Diagnostic Initial Multi-Modules
**Décision:**
- Test adaptatif par module (~10 min/module)
- Réussir → test niveau supérieur
- Échouer → test niveau inférieur
- Objectif: cartographier précisément les acquis et lacunes

**Justification:**
- Modèle EvidenceB — rapide et précis
- Pas de 45-min test initial (trop long pour enfants)
- Divise en modules = moins overwhelm

---

### ✅ Decision 4.2: Parcours Conditionnel (Mastery-Based)
**Décision:**
- L'élève ne peut passer au concept suivant que si le précédent est maîtrisé
- Tests intermédiaires rigoureux
- Mastery regression possible (modélise l'oubli)

**Pourquoi:**
- Fondation pédagogique solide
- Prévient l'accumulation de lacunes
- Aligné avec программа national (progression linéaire)

---

### ✅ Decision 4.3: Assistance Multi-Niveaux
**Décision:**
```
Échec répété → 
  1. Ressources alternatives (vidéo, explication différente)
  2. Requête asynchrone (message écrit)
  3. Peer-to-peer (appel à un camarade)
  4. Expert pédagogique (intervention ponctuelle)
```

**Justification:**
- Zéro abandon — toujours une issue
- Gradation = pas de sur-dependance
- Maintient l'autonomie de l'élève

---

## 5. Contenu Pédagogique

### ✅ Decision 5.1: Alignement Programme National
**Décision:** Contenu structuré en miroir du programme algérien

```
Matière → Niveau (CP/CE1/CE2/CM1/CM2) → Domaine → Compétence
```

**Justification:**
- Pertinence pour les élèves et parents
- Facilite l'adoption scolaire
- Partenariat potentiel avec ministère

---

### ✅ Decision 5.2: IA Générative — Phase 1 LIMITÉE
**Décision:**
- Utiliser IA pour: exercises adaptatifs, feedback personnalisé
- NE PAS utiliser pour: contenu pédagogique principal (Phase 1)
- Curation humaine obligatoire pour tout contenu Arabic

**Justification:**
- Risque de biais dans le contenu généré
- Manque de validation scientifique
- Pas assez de données Algerian-specific pour fine-tuning

**Pour Phase 2+:**
- Exploration IA générative pour création de contenu
- Partenariats avec éditeurs locaux
- Fine-tuning sur données Algerian educational

---

## 6. Points EN COURS de Validation

| Sujet | Status | Dtails |
|-------|--------|--------|
| Stack technique exact | 🔄 À décider | Node.js? Python? |
| Hébergement/Cloud | 🔄 À discuter | Budget, localisation données |
| Partenariat ministère | 🔄 À initiator | Timing, arguments |
| Contenu initial | 🔄 À valider | Quels modules en priority |
| Business model | 🔄 À discuter | B2C, B2G, freemium? |

---

*Ce document reflète les décisions validées à date. Toute modification doit être documentée ici.*
