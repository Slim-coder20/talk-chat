# Talk

Application de chat en temps réel : salons publics, conversations privées et authentification par e-mail, construite avec React, TypeScript et Supabase.

**Démo en ligne :** <https://talk-six-lyart.vercel.app>

## Fonctionnalités

- **Authentification** : inscription, connexion et déconnexion par e-mail et mot de passe (Supabase Auth).
- **Mot de passe oublié** : envoi d'un lien de réinitialisation par e-mail, puis page dédiée pour choisir un nouveau mot de passe.
- **Salons** : liste des salons existants et création d'un nouveau salon.
- **Conversations privées** : liste des utilisateurs pour démarrer une discussion à deux.
- **Messages en temps réel** : les nouveaux messages s'affichent sans recharger la page, grâce aux abonnements Supabase Realtime.
- **Interface responsive** : navigation adaptée au mobile.

## Stack technique

| Rôle | Outil |
|---|---|
| Interface | React 19, TypeScript, CSS Modules |
| Build | Vite 6 |
| Routage | React Router 7 |
| Données serveur | TanStack Query (React Query) |
| État global | Zustand (utilisateur connecté, discussion active) |
| Formulaires | React Hook Form |
| Notifications | React Toastify |
| Backend | Supabase (Auth, PostgreSQL, Realtime) |
| Intégration continue | GitHub Actions (lint et build) |
| Hébergement | Vercel |

## Installation

Prérequis : Node.js (version LTS) et un projet [Supabase](https://supabase.com).

```bash
git clone https://github.com/Slim-coder20/talk-chat.git
cd talk-chat
npm install
```

Crée un fichier `.env.local` à la racine avec les identifiants de ton projet Supabase :

```bash
VITE_SUPABASE_URL=https://ton-projet.supabase.co
VITE_SUPABASE_ANON_KEY=ta-cle-anon
```

Le projet Supabase doit contenir les tables `rooms`, `messages` et `profiles`, avec Realtime activé sur `messages`.

```bash
npm run dev
```

## Scripts

| Commande | Effet |
|---|---|
| `npm run dev` | Lance le serveur de développement |
| `npm run build` | Vérifie les types puis construit l'application |
| `npm run lint` | Analyse le code avec ESLint |
| `npm run preview` | Sert la version construite en local |

## Structure

```text
src/
├── App.tsx              # Synchronise la session Supabase et le store
├── supabaseClient.ts    # Client Supabase
├── store/chatStore.ts   # Store Zustand : utilisateur et discussion active
├── components/
│   ├── auth/            # Connexion, inscription, mot de passe oublié
│   ├── chat/            # Affichage et envoi des messages
│   └── Dashboard.tsx    # Routes de l'espace connecté
└── pages/               # Salons, création de salon, conversations, réinitialisation
```

La logique d'authentification est détaillée dans [doc/gestion-utilisateur.md](doc/gestion-utilisateur.md).

## Auteur

Slim Abida — [portfolio](https://www.slim-abida.dev) · [LinkedIn](https://www.linkedin.com/in/slim-abida-50161a35b/)
