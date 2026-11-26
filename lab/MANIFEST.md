# Manifeste du laboratoire Virology

Le sujet Epitech *Virology* v1.3 demande de démontrer un outil sur une VM Windows et d’expliquer les résultats du point de vue de l’opérateur et du défenseur. Ce manifeste fixe l’environnement de départ et les éléments à relever pour la démonstration. Les pages citées correspondent à la numérotation du fichier `virology-project.pdf`.

## Environnement retenu

| Élément | Choix | État |
| --- | --- | --- |
| Hyperviseur | Oracle VirtualBox | Version installée `7.2.22.175245`, relevée sur l’hôte. |
| Machine cible | `virology-clean`, 4 processeurs virtuels et 4 Gio de RAM | `winver` confirme Windows 11 Entreprise (évaluation) 64 bits, version 26H2, build `26300.9457`. Bureau Windows affiché en configuration hors ligne. |
| Snapshot de départ | `virology-reference` | Créé le 26 novembre 2026 à 15 h 44 min 45 s, heure de Paris. VirtualBox le désigne comme snapshot courant. La VM était arrêtée proprement. |
| Antivirus de référence | Microsoft Defender Antivirus | Protection en temps réel active. Signatures `1.437.1.0`, datées du 17 septembre 2025. Dernière mise à jour affichée comme indisponible. Version du moteur à relever avant l’essai. |
| Journaux à consulter | Journaux Windows Système et Sécurité, historique de protection de Microsoft Defender | Le 26 novembre 2026, Système et Sécurité ont été ouverts dans l’Observateur d’événements. Dans Sécurité Windows, l’historique de protection affichait « Aucune action récente ». |
| Capture réseau | Wireshark `4.6.10` installé sur l’hôte | Le 26 novembre 2026, lecture d’un fichier `.pcapng` contenant une requête DNS fictive pour `example.invalid` vérifiée dans Wireshark. Le pilote Npcap est absent. La capture en direct reste à valider. |

La VM est l’environnement commun aux deux rôles. La **Red Team** joue le rôle de l’opérateur et décrit le comportement attendu. La **Blue Team** joue le rôle du défenseur et décrit les événements qu’elle peut observer. Utiliser des comptes et des données de démonstration fictifs dans l’environnement dédié.

### Relevé initial dans Windows

- Relevés effectués dans `winver` et **Sécurité Windows** avant l’arrêt de la VM et la prise du snapshot.
- Les gels VirtualBox en mode NEM ont nécessité un contournement temporaire pendant la configuration et le relevé. Le 26 novembre 2026, le démarrage normal a atteint le bureau et l’Observateur d’événements a chargé les journaux Système et Sécurité sans ce contournement. Certaines commandes ont répondu avec un délai.

## Critères du sujet et preuves attendues

Le **socle obligatoire** figure à la page 3. Pour chaque ligne, relever la date et l’heure de l’essai, la version du binaire, le résultat observé et la référence de la preuve. Les observations ci-dessous décrivent les critères à évaluer.

| Critère | Observation attendue | État |
| --- | --- | --- |
| Fonctionnement discret et absence de détection par l’antivirus déclaré | État de la protection et alertes éventuellement observées pendant l’essai. La conclusion porte sur cet essai et cette configuration. | À vérifier |
| Shell distant | Résultat de la démonstration encadrée sur la VM déclarée. | À vérifier |
| Canal utilisant un protocole existant | Protocole déclaré et trafic correspondant identifiable dans une capture. | À vérifier |
| Récupération d’identifiants | Résultat de la démonstration encadrée sur des données de labo fictives. | À vérifier |
| Survie à un redémarrage | Retour du programme observé après le redémarrage de la VM. | À vérifier |
| Reprise après arrêt du processus | Retour du programme observé alors que Windows est resté en fonctionnement. | À vérifier |
| Communications chiffrées | Preuve dans une capture, par exemple Wireshark. Le sujet exprime une préférence pour une méthode asymétrique. | À vérifier |
| Rollback sélectif des traces système, réseau et commandes | Compte rendu encadré qui distingue les traces visées de celles qui ont été préservées. | À vérifier |

La page 4 présente les **capacités étendues** après le socle. Elle cite `keylog`, `rdp`, `crack`, `pth`, `loot`, `phish`, `propagate`, `privesc`, `syscall`, `shell` intégré et `whatever`. Le shell intégré est une extension distincte du shell distant du socle. Le sujet autorise les bibliothèques de bas niveau et exclut les outils tout-en-un comme solution finale. Si un outil connu est utilisé au départ, le sujet demande de documenter son impact sur la détection, puis de le remplacer par une implémentation propre à l’équipe.

## Livrables à vérifier avant le rendu

Les critères de rendu de la page 5 s’appliquent aux éléments suivants.

- [ ] Outil fonctionnel présenté en direct sur la VM Windows du labo.
- [ ] README avec installation, utilisation, ressources externes et sources.
- [ ] Identifiant de tactique ou de technique MITRE ATT&CK et courte note Blue Team pour chaque capacité implémentée.
- [ ] Manifeste permettant de retrouver les conditions de départ de la démonstration.
- [ ] Livraison organisée, avec les fichiers utiles et sans artefacts temporaires, binaires ou de test superflus.
- [ ] Code maintenable, avec des responsabilités claires et des défauts évidents corrigés.
- [ ] Historique Git cohérent, au moins trois branches et au moins deux commits par membre.
- [ ] Présentation courte, appuyée par des slides exactes.

## Fiche de relevé pour chaque essai

| Date, heure et fuseau | Critère | Build testé et snapshot | Observation Red Team | Observation Blue Team | Preuve associée |
| --- | --- | --- | --- | --- | --- |
| À renseigner | À renseigner | À renseigner | À renseigner | À renseigner | À renseigner |
