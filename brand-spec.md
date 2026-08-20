# Brand spec — Rayan Toufella · Software Engineer (Backend & AI)

Source : palette « Eclipse / Neon Teal » — mode sombre, fond quasi noir,
accent néon teal unique + cyan secondaire. Inspirée des portfolios developer
2025-2026 (Hemanth Chakravarthy, Yash Ahire, Ben Scott) : fond sombre profond
(jamais de noir pur), un seul accent néon, typo géométrique massive (Space Grotesk).
Dérivés calculés en OKLch via `color-mix()` — aucune couleur hors tokens.

## Tokens OKLch

| Token           | Valeur                       | Rôle                                             |
|-----------------|------------------------------|--------------------------------------------------|
| `--bg`          | `oklch(0.163 0.009 264.3)`   | Fond principal — quasi noir froid                |
| `--surface`     | `oklch(0.200 0.013 264.2)`   | Panneaux / cartes                                |
| `--fg`          | `oklch(0.985 0.000 89.9)`    | Texte principal — blanc pur adouci               |
| `--muted`       | `oklch(0.672 0.021 263.0)`   | Texte secondaire                                 |
| `--border`      | `oklch(0.260 0.020 264.1)`   | Filets hairline                                  |
| `--accent`      | `oklch(0.804 0.137 184.2)`   | Teal néon `#24DBC9` — un seul accent             |
| `--accent-bright` | `oklch(0.832 0.117 218.7)` | Cyan clair `#61DAFB` — rehauts code/mentions     |
| `--accent-teal` | `oklch(0.715 0.126 215.2)`   | Cyan `#06B6D4` — secondaire (bordures, dégradés) |

Dérivés : `--accent-ink` (teal utilisé comme « encre » accent sur fond sombre),
`--on-accent` `#05201B` (texte très sombre posé sur le teal — boutons CTA,
contraste 9.8:1), `--ink` `#07080C` (fond le plus profond), `--steel` `#3E4756`
(lignes et connecteurs décoratifs).

## Typographies

- **Display (titres)** : Space Grotesk 700, tracking serré `-0.03em` — grosse
  typo géométrique, héro du design (H1 jusqu'à 88px).
- **Corps** : Outfit 400/500 — lisible, neutre, moderne.
- **Mono** : ui-monospace / JetBrains Mono / SF Mono — code, terminal, chiffres,
  eyebrows, étiquettes.

## Langage visuel

1. Un seul accent teal `#24DBC9` sur fond quasi noir — jamais plus de deux
   occurrences accentuées à l'écran (eyebrow + CTA principal).
2. Pas de noir pur : fonds `#0C0E12` / `#07080C` (cf. guide dark mode 2026).
3. Dégradé de texte accent → cyan clair pour les mots-clés (ex. « Backend & AI »).
4. Bordures coniques animées sur les cartes d'IA (anneau teal/cyan en rotation),
   rendu masqué par `mask-composite` — dégradation silencieuse si non supporté.
5. Motifs techniques : terminal, code, JSON structuré, constellation de particules
   canvas dans le héros, lignes SVG qui se dessinent, icônes monoline.
6. Contraste exigé : texte corps ≥ 7:1, texte accent ≥ 4.5:1, texte sur accent
   ≥ 4.5:1 (vérifié : `--fg`/`--bg` 18.5:1, `--muted`/`--bg` 6.5:1,
   `--on-accent`/`--accent` 9.8:1).

## Animations dynamiques

1. **Révélation lettre par lettre** des titres (stagger par lettre, `data-split`).
2. **Constellation de particules** canvas dans le héros (nœuds + liens teal,
   pause hors écran).
3. **Spotlight souris** : halo radial teal qui suit le curseur.
4. **Boutons magnétiques** sur les CTA (suivent légèrement le curseur).
5. **Sheen** : balayage lumineux sur les boutons primaires au survol.
6. Marquee, tilt 3D, frappe de terminal, barre de progression, draw SVG, stepper.
7. Tout est désactivé ou figé sous `prefers-reduced-motion` et sur les
   appareils sans pointeur fin.