# quiz-site

Depot Git relie par deploiement automatique (GitHub Actions -> FTP) au dossier OVH `mentaal-git` (site quiz.bilan-mdph.fr).

Etat au 18/09/2026 :
- Le pipeline de deploiement automatique est en place (voir `.github/workflows/deploy.yml`), suivant exactement le meme modele que les autres sites du cabinet.
- - Ce depot ne contient PAS encore une copie des 8 tests actuellement en ligne (gad-7, rses, dass-21, phq-9, pcl-5, pswq, asrs, tas-20). Ces fichiers existent uniquement sur le serveur OVH pour l'instant.
  - - Comme le deploiement ne supprime jamais les fichiers presents sur le serveur mais absents du depot (sauf option dangereuse explicitement desactivee ici), le premier deploiement ne touchera pas les tests deja en ligne.
    - - Pour que ce depot reflete vraiment le site (et permettre de le modifier par Git), il faudra y ajouter le contenu des 8 tests existants, puis eventuellement les nouveaux tests construits dans l'apercu Claude.
     
      - A faire par Max : ajouter les trois secrets du depot (Settings -> Secrets and variables -> Actions) : FTP_SERVER, FTP_USERNAME, FTP_PASSWORD.
