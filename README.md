  AntiScamBot – L’IA qui fait perdre leur temps aux arnaqueurs
AntiScamBot est un projet Python innovant qui utilise l’intelligence artificielle, la reconnaissance vocale et la synthèse vocale pour simuler une victime crédible lors d’appels frauduleux. Le but : faire perdre un maximum de temps aux escrocs, en jouant un personnage attachant, naïf et distrait.

  Objectif
L’objectif principal est de dissuader les arnaqueurs en les piégeant dans de longues conversations inutiles, tout en collectant des données utiles à des fins de sensibilisation, d’analyse ou de prévention.

  Fonctionnalités
🎭 Personnalité simulée : "JUSTINE FOREST", 65 ans, naïf, bavard, à la retraite depuis 2 ans.
🎤 Reconnaissance vocale (Speech-to-Text) via Google Cloud Speech-to-Text.
💬 Génération de réponses contextuelles avec un LLM (Qwen2.5-32B via Nebius).
🎙️ Synthèse vocale naturelle avec Google Cloud Text-to-Speech.
🤖 Détection d’émotions dans les paroles de l’arnaqueur pour adapter le comportement :
- Impatient → Confusion
- Agressif → Hésitation
- Amical → Enthousiasme
🧏 Gestion intelligente des silences et hésitations.
🎲 Réponses variées (courtes, longues, digressions, hésitations, lapsus).
📼 Enregistrement des conversations audio et texte pour analyse. 

   Architecture du projet
   🎤 Micro → [Google STT] → 🎯 Analyse (Emotion + Intention) → [Historique messages + Contexte personnage] → 🤖 LLM (Qwen2.5-32B via Nebius) → 🔊 Google Text-to-Speech (voix réaliste) →🎧 Lecture réponse

  Prérequis
- Python 3.9+
- Un compte Google Cloud avec une clé JSON (activée pour Speech-to-Text et Text-to-Speech)
- Une clé API Nebius pour le modèle LLM
- Microphone et haut-parleurs fonctionnels
- Environnement virtuel recommandé

  Installation
Installer/exporter toutes les dépendances/librairies qui permettrons l'éxécution du code. Comme: python -m venv venv; pip install -r requirements.txt; pip install sounddevice; ect...

  Configuration
Crée un fichier key.json contenant tes identifiants Google Cloud (STT et TTS).
Renseigne ta clé Nebius dans le code : provider="nebius",
    api_key="VOTRE_CLÉ_ICI",

  Lancer le bot
En utilisant: python michel_bot.py

📁 Fichiers principaux
michel_bot.py : Script principal du bot
key.json : Clé de l'API Google (à ne pas versionner)
output.mp3 : Réponse vocale générée
voice.flac : Entrée vocale de l’escroc

