# Analyse augmentée à l’aide du Machine Learning

## Introduction

L'une des caractéristiques les plus sophistiquées de l'offre d'Oracle Analytics est la possibilité d'exploiter l'analyse avancée et l'apprentissage automatique en cliquant sur un bouton, directement à partir de vos projets libre-service et de vos datasets. Les fonctions d'apprentissage automatique comprennent un ensemble d'algorithmes prédéfinis qui peuvent être utilisés pour extraire des informations de vos ensembles de données, telles que l'analyse des sentiments, l'analyse des séries temporelles, les résultats des prédictions et les scores de confiance.

Les fonctions analytiques avancées telles que les prévisions, l'analyse des tendances et le regroupement peuvent être appliquées à la visualisation dans votre canevas en un seul clic. En outre, les utilisateurs peuvent appeler des scripts d'apprentissage automatique personnalisés en utilisant la fonction d'évaluation des scripts à partir de vos projets en libre-service ou en ajoutant des scripts personnalisés dans le cadre de votre flux de données lors de la préparation des données..

## Utiliser le Machine Learning pour accélérer l’analyse

Dans ce chapitre, nous allons importer un ensemble de données contenant plusieurs enregistrements d'employés avec divers attributs qui enregistrent l'expérience, la performance et les incitations des employés. Les données sont historiques et comprennent un élément qui identifie si l'employé a quitté l'organisation.

-   Notez la colonne d'attrition, un indicateur binaire.
-   Chaque enregistrement d'employé contient une réponse "oui" ou "non".

Une fois que vous avez importé vos données dans Oracle Analytics, vous commencez par le profilage des données et l'examen des recommandations sémantiques pour réparer et enrichir vos données en vue d'une analyse plus approfondie. Ensuite, vous tirerez parti d'une capacité d'analyse améliorée appelée explain. Explain est utilisée pour générer des informations via une combinaison de traitement du langage naturel, de statistiques descriptives et de techniques de modélisation prédictive afin de mieux comprendre nos données et d'obtenir des informations plus approfondies avant notre analyse.

1.  sélectionnez Create .. Workbook.

    !["oaslandingpage"](518a3accf5c1505328cc14a1b15f7809.png)

2.  sélectionnez Create Dataset.

    !["createdataset"](59275ff9fecb8433670dec5e3a66c044.png)

3.  Sélectionnez le fichier *“AttritionTrainingV3.xlsx”*

    !["draganddropattritiontrainingv3xlsxfiletoaddthedataset"](4f8503453e24db49da9d9ad24878b931.png)

    Cliquez sur Ok pour ajouter le fichier au dataset.

    ![](864464fe6fd02fd2eac8a7696d56fd36.png)

    Une fois fait, enregistrez le fichier et nommer le « AttritionTrainingV3 ».

4.  Maintenant, localisez la colonne ID et cliquez sur l'icône hamburger en haut de la colonne. Cachons cette colonne puisque la colonne ID n'a aucune incidence sur le fait qu'un employé reste ou quitte notre organisation.  
    **Remarque** : cette même procédure peut être appliquée à toute colonne dont vous pensez qu'elle n'a pas d'incidence sur l'attrition.

    !["hidetheidcolumn"](dc0787c7511056b0d945b6d6a39617c3.png)

    De même, trouvez la colonne Age et, à l'aide du panneau des propriétés dans le coin inférieur gauche, modifiez "Treat As" en Attribute et "Data Type" en Text. La raison en est que l'âge d'un employé peut effectivement avoir une incidence sur l'attrition, de sorte que l'évaluation de chaque âge distinct d'un employé pourrait être déterministe.

    !["changeagecolumntoanattributeandit'sdatatypetotext"](660a6187ad4cc4ed201e1d3066b24b37.png)

    Oracle Analytics affiche un ensemble de transformations de colonnes utiles appelées "Recommandations" lorsqu'il détecte des modèles dans vos données. Ces recommandations sont affichées dans un volet à droite. Trouvez la colonne SSN et sélectionnez la recommandation "Obfuscate Digits of SSN" (obscurcir les chiffres du SSN) pour cacher ces informations sensibles aux regards indiscrets. Enregistrez les modifications que nous avons apportées au dataset Attrition.

    !["findthessncolumntoviewoasrecommendationthenchooseobfuscatedigitsofssnoption"](1cd209a6bd626da0076898b7297544d6.png)

    **Remarque** : ces recommandations utiles représentent un élément clé de différenciation pour Oracle et sont conçues pour améliorer la productivité de l'utilisateur final tout en aidant les clients à mieux exploiter leurs données.

5.  Créons maintenant un workbook à l'aide du dataset que nous venons d'améliorer en cliquant sur le bouton "Create Workbook" en haut à droite.

    !["clickcreateworkbook"](471498d89a75bf7f11c5ea1d909c00b0.png)

    Un nouveau classeur sera ouvert et le focus devrait être mis sur "Visualize" par défaut. Si ce n'est pas le cas, il suffit de choisir "Visualize" en haut de la page

    !["choosevisualize"](953fb551ca11b3395ca61e7e86dfdd89.png)

    Dans le panneau "Data Elements" sur le côté gauche, trouvez l'attribut Attrition, puis cliquez dessus avec le bouton droit de la souris et sélectionnez "Explain Attrition" (expliquer l'attrition).

    !["explainattritionafterrightclickingonthatattribute"](0e67700d0c3897e23eca82eb09b2525f.png)

6.  Cette opération génère une fenêtre d'explication qui fournit des informations sur l'attrition. Ces informations sont divisées en 4 catégories. La première catégorie identifie les faits de base concernant notre attribut d'attrition. Dans ce cas, elle effectue des agrégations automatiques sur les lignes distinctes.

    !["piechartshowingcountofemployeeswholeavethecompany"](caa41e1c0718f1efb9126cb63d438eac.png)

    L'attrition étant une variable binaire "oui/non", elle présente un diagramme circulaire montrant la répartition des employés qui ont quitté l'entreprise ou qui ne l'ont pas fait. Faites défiler vers le bas pour découvrir d'autres graphiques générés par Explain. Vous pouvez sélectionner toute information intéressante que vous souhaitez partager ou analyser plus en détail en cliquant sur la coche située dans le coin supérieur droit de chaque graphique.

    Naviguez jusqu'au deuxième onglet, qui identifie les facteurs clés liés à l'attribut d'attrition. Oracle Analytics s'appuie sur l'apprentissage automatique pour identifier les variables ayant la relation la plus déterministe avec les facteurs d'attrition. Les graphiques à barres fournissent une distribution de l'attrition pour chaque facteur clé.

    !["keydriversofattrition"](b003646473816c32c7cdb07b1278ea84.png)

    **Remarque :** Ne pas tenir compte de l'ordre et de l'emplacement de l'écran pour les graphiques livrés via "Expliquer".

    Explain génère également des informations sur les segments, en identifiant les similitudes ou en regroupant les scénarios de profil dans lesquels il est plus ou moins probable que l'attrition soit un oui ou un non.

    !["segmentsdrivingattrition"](384046981c83177e1673d333bb2b3aa7.png)

    Vous pouvez utiliser le menu déroulant pour passer d'un groupe de segments à l'autre afin d'identifier le degré de confiance du scénario.

    La quatrième catégorie d'informations illustre les anomalies de l'attrition ou des éléments peut-être inattendues. L'indicateur d'anomalie indique les combinaisons de chaque valeur distincte d'attrition par rapport à toutes les colonnes de l'ensemble de données, ce qui permet de mettre en évidence les valeurs aberrantes.

    !["unexpectedanomaliesofattrition"](ee41f7b8afd1b99373d34835cb5de3e7.png)

    Il visualise la valeur réelle et la valeur attendue, en mettant en évidence les endroits où la valeur réelle et la valeur attendue ne correspondent pas.

    Sélectionnez les graphiques suivants dans les onglets affichés par Explain:

    -   Attrition pie chart depuis le panneau Basic facts about Attrition
    -   JobRole & Overtime depuis le panneau Key Drivers of Attrition
    -   JobRole depuis le panneau Anomalies of Attrition

        **Remarque :** il se peut que vous deviez cliquer sur Rafraîchir l'affichage en bas du panneau Anomalies de l'attrition pour voir tous les graphiques générés.

Cliquez maintenant sur "Add Selected" en haut à droite pour ajouter ces visualisations à votre workbook. Le résultat devrait être un canevas nommé Explain Attrition contenant les visualisations que vous avez sélectionnées et que vous pouvez explorer davantage ou partager.

!["canvasofitemsselected"](cc015128e7cc900c5f743066a1c898bb.png)

7.  Nous pouvons exécuter la fonction "explain" sur d'autres attributs ou mesures de notre ensemble de données. Lorsque vous exécutez "explain" sur un élément de données, un nouveau canevas est ajouté au classeur. Essayez d'expliquer l'attribut "EducationField" et sélectionnez quelques visualisations pour créer un nouveau canevas.

    !["explaineducationfield"](529818d554614cd1b7e99635ab8fe847.png)

    Sélectionnez les graphiques suivants en fonction des résultats obtenus concernant EducationField:

    -   EducationField pie chart depuis le panneau Basic Facts about EducationField
    -   Department and JobRole depuis le panneau Key Drivers of EducationField
    -   Overtime anomalies chart depuis le panneau Anomalies of EducationField

**Remarque** : il se peut que vous deviez cliquer sur Rafraîchir l'affichage au bas du panneau Anomalies de EducationField pour voir tous les graphiques générés.

Cliquez sur "Add Selected" et un nouveau canevas pour EducationField sera ajouté au workbook, ce qui nous aidera à améliorer notre compréhension de l'attrition.

Avant de passer au chapitre suivant, enregistrez ce workbook en lui donnant un nom tel que *Attrition Analysis*

!["canvasofexplaineducationfield"](2ea8c8aadd25610d5d34f1131606dc4d.png)

8.  Explorons plus avant l'attrition du dataset. Un élément que nous n'avons pas encore analysé en profondeur est le genre. Ajoutez un canevas à votre workbook en cliquant sur le signe + en bas de l'écran et renommez le canevas "Gender Analysis".

    !["renamenewcanvasgenderanalysis"](e14d77aefdadff1a14652f6af8bd4975.png)

    Utilisez la barre de recherche située en haut à gauche dans le panneau du dataset pour générer une visualisation basée sur les éléments Gender:

    !["searchbar"](33b06bdf1ad0c604abb0253d26d04879.png)

    La recherche vous permet d'interroger votre dataset et de créer des visualisations basées sur les mesures et les attributs qui vous intéressent. Saisissez les noms de colonnes suivants : "EmployeeCount", "Attrition" et "Gender", en sélectionnant chaque colonne au fur et à mesure qu'elle apparaît. La fonction d'auto-complétion de la recherche est très pratique, de sorte qu'il suffit souvent de taper une partie du nom de la colonne pour la trouver. Sélectionnez chaque colonne au fur et à mesure qu'elle apparaît et ajoutez-la à la barre de recherche.

    Une fois les trois colonnes affichées dans la barre de recherche, il suffit de les faire glisser sur le canevas vide ou de choisir de créer une visualisation sous la barre de recherche, ce qui permet d'obtenir la visualisation suivante:

    !["createvisual"](ca2318a587b9d0662ecd1957a71ebd5b.png)

    Le résultat final devrait ressembler à ceci:

    !["barchartofattriton,genderandemployeecount"](cabcc15adeb6d9713a5aa1597ac19bd4.png)

    Nous constatons qu'en chiffres bruts, plus d'hommes que de femmes ont quitté notre organisation. Changeons de type de graphique pour déterminer proportionnellement le nombre d'hommes et de femmes qui ont quitté l'organisation. Il est facile de modifier le type de graphique en sélectionnant un autre graphique à l'aide des icônes situées en haut à droite du graphique ou dans le panneau de mise en page du graphique. Quelle que soit la méthode utilisée, modifiez la présentation du graphique pour en faire un diagramme à barres horizontales empilées à 100 %. Ensuite, il suffit de faire glisser le genre vers la catégorie (X-Axis) et l'attrition vers la couleur pour que nous puissions voir le pourcentage d'hommes et de femmes qui quittent l'entreprise ou qui restent, comme indiqué ci-dessous:

    !["swapx-axiswithcolor"](b830b5f5ab76fed3b6c01734e125f699.png)

    Utilisons maintenant une fonction d'analyse avancée en un seul clic pour approfondir la question du genre. Dans le panneau des éléments de données, utilisez la touche multisélection de votre ordinateur pour sélectionner *Gender*, *EnvironmentSatisfaction*, *WorklifeBalance*, et *Last Name*. quez ensuite avec le bouton droit de la souris et choisissez l'option *Scatter* chart. Finalement, déplacez *Gender* vers Trellis Columns. Votre visualisation devrait ressembler à ceci:

    !["choosescatterchartandmovegendertotrellisrows"](94d8a3f8ab612b715a76dc0c3837376f.png)

**Remarque :** vous pouvez simplement faire glisser une visualisation au-dessus, au-dessous ou à côté d'une autre visualisation pour les ordonner comme vous le souhaitez.

À n'importe quel endroit du diagramme de dispersion, cliquez avec le bouton droit de la souris et choisissez *Add Statistics .. Outliers*. Les valeurs aberrantes seront mises en évidence par des couleurs différentes pour faciliter leur identification.

!["addoutliers"](6d458c84e0b343a603d3cc22becc0730.png)

Si l'on considère les employés qui ne sont pas dans les valeurs aberrantes (ce qui représente la majorité), on constate que les femmes semblent avoir un niveau de satisfaction environnementale et d'équilibre entre vie professionnelle et vie privée inférieur à celui de leurs homologues masculins. Il s'agit peut-être d'un facteur clé pour comprendre ce qui pousse les femmes à quitter notre organisation.

Sauvegardez votre analyse.

## Tirer parti du Machine Learning dans Oracle Analytics Server pour prévoir les départs volontaires

Cet exercice explorera comment le machine learning en libre-service permet l'analyse prédictive en utilisant les modèles d'apprentissage automatique natifs contenus dans Oracle Analytics Server. Nous allons maintenant étendre notre analyse en voyant comment nous pouvons prédire si un employé est susceptible de quitter l'organisation. Pour ce faire, nous utiliserons un modèle de classification binaire. Avant de nous aventurer plus loin, essayons de comprendre brièvement ce qu'est la classification binaire.

La classification binaire est une technique qui consiste à classer les éléments d'un ensemble de données donné en deux groupes sur la base de règles de classification, par exemple la prédiction de l'attrition des employés, c'est-à-dire si l'on s'attend à ce que l'employé parte ou ne parte pas. Ces règles de classification sont générées lorsque nous formons un modèle à l'aide d'un ensemble de données de formation qui contient des informations sur les employés et indique si l'employé a quitté l'entreprise ou non.

1.  Sur la page d'accueil, cliquez sur le bouton Create et sélectionnez Dataflow.

    !["createdataflow"](4c82dad206c88b94a20cf27b05cb782c.png)

2.  Sélectionner le dataset que nous analysons “Attrition Training V3.” et cliquez sur Add.

    !["chooseattritiontrainingv3dataset"](082c4b4666d087dc188c087c223b75dd.png)

3.  Ce dataset sera ajouté en tant que source d'information pour notre data flow.

    !["datasetattritiontrainingv3 "](abf44434d438788b15d0004bcf764367.png)

4.  Dans le dernier exemple, nous avons constaté qu'il y avait de l'attrition dans notre département et nous avons pris note de certains des facteurs identifiés à l'aide de la fonction d'explication. Ce que nous voulons faire maintenant, c'est construire et entraîner un modèle d'apprentissage automatique pour prédire si quelqu'un est susceptible de quitter l'organisation. Ajoutons un algorithme de machine learning à notre flux de donnée.

    Sélectionnez l’icone *plus*  sur les données sources et sélectionnez *Train Binary Classifier*.

    !["trainbinaryclassifiermodel"](e720e606bf678b6ddf73bb82dc796858.png)

5.  Sélectionnez *Naïve Bayes for Classification* et cliquez OK.
6.  Sélectionnez l’attribut *Attrition* comme colonne cible du modèle. Assurez-vous que la classe positive est *Yes* et laisser les autres options par défaut.

    !["targetcolumnsisattrition"](b4799710103230cdd48fc1baa8485d10.png)

7.  Cliquez *Save Model* et donnez au modèle un nom comme "AttritionPredict-BC-NB".

    !["savemodelasattritionpredict-bc-nb"](9f5c532670463b9c0f9f5bc8a33493c3.png)

8.  Sauvegardez votre Data Flow avec un nom comme *AttritionPredict-BC-NB* ou similaire

    !["savedataflowasattritionpredict-bc-nb"](0aecacbcffc28ac22654c9d6864b0a53.png)

9.  Exécutez le Data Flow une fois qu'il a été enregistré. Attendre la fin du Process.

    !["rundataflow"](8e9515a3cb18e2f83bc93ac294cd2e29.png)

10. Quittez le Data Flow et à partir de la page d'accueil , Ouvrez l'onglet Machine Learning pour examiner les résultats du modèle de classification.

    !["machinelearningsection"](b19d9d3127ee87ed4543ba2576bd0de2.png)

11. Nous pouvons vérifier la validité de notre modèle de machine learning .Cliquez sur les points situés sur le côté droit et sélectionnez "Inspect".

    !["attritionpredict-bc-nbmodelinspectoption"](35f77e900f83a9c8a717581b2b26c260.png)

12. Nous pouvons inspecter le modèle pour voir plus de détails comme la qualité du modèle (matrice de confusion, précision, rappel) et les dataset générés.L'onglet qualité identifie la qualité globale du modèle à l'aide d'une série de mesures connexes : La précision globale du modèle est de 87% et la précision est de 65%.

    !["reviewqualityofthemodel"](03ecdb105264dea75c1c3ae1b46a2c5a.png)

13. Étant donné que le modèle a obtenu un taux de precision de 87 %, appliquons-le à un ensemble de données d'employés qui restent dans notre organisation pour voir lesquels d'entre eux pourraient être enclins à partir. Cliquez sur les trois points en haut à droite, puis sur sélectionnez *Import Workbook/Flow*.

    !["importworkbookflow"](335bdf655d56df59857d5d9c0e8afb66.png)

14. sélectionnez le fichier *Employee-Analysis.dva* .

    !["employee-analysisdvafile"](344f38543b37737ef6960d3df289ddb2.png)

15. Entrez le mot de passe *“Admin123”*.

    !["passwordprompt"](3f8f2c780901c99c91eb87360641b27a.png)

16. Recherchez et ouvrez le workbook intitulé Employee Analysis. Nous disposons ici d'un workbook existant qui présente 470 employés au sein de notre organisation. Nous allons appliquer notre nouveau modèle de formation à la classification à cet ensemble de données que nous avons importé avec ce workbook.

    !["employeeanalysisworkbook"](3d17081b40379b0e2cc5fb74c2e5fafb.png)

17. Allez dans l'onglet Accueil et créez un nouveau *data flow*.

    !["createdataflow"](4c82dad206c88b94a20cf27b05cb782c.png)

18. Sélectionnez le nouveau dataset “Attrition Predict”.

    !["attritionpredictdataset"](60b1d64584f25014705a7e5cb8cb66c2.png)

19. Cliquez sur l’icône *plus icon* .

    !["plusicontorightofdataset "](38157825a53a2cc29c91a4469dd2755c.png)

20. Sélectionnez *Apply Model* .

    !["applymodelicon"](cbe9961abd0749caae5a2741f67830e4.png)

21. Sélectionnez notre modèle de Machine Learning et cliquez OK.

    !["attritionpredict-bc-nbmodel"](560d43181bb605f295294925d295cc1b.png)

22. Notre modèle d'application comportera 3 sections.
    -   **Outputs** - il s'agit d'une liste de colonnes renvoyées par le modèle en plus des colonnes d'entrée. L'application du modèle enrichira notre dataset sur les employés en ajoutant une valeur prédite et un score de confiance de prédiction.
    -   **Parameters** - Les paramètres facultatifs que les utilisateurs peuvent passer pour appliquer le modèle.
    -   **Inputs** - Il s'agit des colonnes d'entrée du modèle pour l "apply".

        Le modèle d'application tentera de faire correspondre automatiquement les noms de colonnes dataset d'entrée aux noms de colonnes du modèle..

        !["applymodelconfiguration"](5dd932c1d49894b6cd17ddf4b74b9920.png)

23. Sélectionnez l’icône *plus icon* et sélectionnez *Save Data* .

    !["savedataicon"](63a395d6c420e7a3025293e1c0502add.png)

24. Donnez lui donner le nom “AttritionPredicted”.

    !["savedataconfiguration"](8dfc8809f1cff6b290f5171e1ccf8d12.png)

25. **Remarque** : nous pouvons exécuter ce data flow dans une base de données existante si nous le souhaitons. Pour l'instant, il s'agit du stockage par défaut des datasets.
26. Enregistrez le data flow sous le nom “AttritionPredicted”.

    !["savedataflowasattritionpredicted"](8109900e96096934ba7a73ac57907ba5.png)

27. Une fois le data flow sauvegardé, exécutez-le .

    !["rundataflowicon"](ce73a7d0fdb12b935540a71ebe8398b2.png)

    Cela produira un nouvel dataset qui ajoutera les valeurs prédites à notre dataset existant.

28. Allez à l’onglet "Data" et sélectionnez le nouveau dataset “AttritionPredicted”.

    !["attritionpredicteddataset"](676a7d9d4587e3d503e51e0eaa6dc796.png)

29. Certaines colonnes peuvent être stockées de manière incorrecte. Comme nous l'avons fait dans les exercices précédents, assurez-vous que :

Les colonnes suivantes sont stockées en tant que mesures:

-   PredictionConfidence
    -   EmployeeCount
    -   Le numéro d'employé est un attribut.

        !["attributeeditor"](851967fd27e8b5af137fa11a631f9958.png)

30.  Créez des visualisations comme l'exemple suivant:
    -   Performance Tile pour EmployeeCount
    -   Donut chart pour EmployeeCount par JobRole et Department
    -   Table avec les colonnes EmployeeNumber, First Name, Last Name, PredictionConfidence, PredictedValue

        !["visulizationsoncanvas"](567da9a59c4e27d8168c101adb6ba341.png)

31.  Sauvegardez le workbook en le nommant “AttritionPredicted”.

    !["saveprojectpanel"](515a5b8477e6dbf371fa56597ac59c37.png)

## Tirer parti du machine learning dans la base de données Oracle pour prédire les départs volontaires

Cet exercice explorera comment tirer parti de l'apprentissage automatique de la base de données Oracle (OML) à partir d'Oracle Analytics Server. La principale différence par rapport à l'exercice précédent est que nous avons utilisé un modèle d'apprentissage automatique natif fonctionnant dans OAS pour prédire l'attrition. Si cette approche fonctionne bien avec des quantités limitées de données, elle n'est pas forcément optimale lorsque l'on travaille avec de grandes quantités de données. La base de données Oracle offre des avantages de performance distincts pour l'hébergement de charges de travail d'apprentissage automatique que Oracle Analytics Server ne peut tout simplement pas égaler. La base de données Oracle peut exploiter les constructions en mémoire, le traitement parallèle, les plans de requête sophistiqués, etc. pour fournir un environnement très robuste pour les charges de travail d'apprentissage automatique. Il est également courant dans l'industrie qu'une équipe de développement professionnel forme, teste, évalue et déploie des modèles d'apprentissage automatique dans un environnement de calcul dédié robuste tel que la base de données Oracle. Notre objectif dans cet exercice est donc d'illustrer comment un analyste peut facilement et rapidement exploiter les modèles de machine hébergés dans la base de données Oracle à partir d'Oracle Analytics Server.

Dans ce scénario, nous commencerons par enregistrer un modèle d'apprentissage automatique que nos scientifiques professionnels ont préalablement formé, testé et déployé dans la base de données Oracle. Une fois enregistré, nous appellerons ce modèle pour prédire qui, dans notre organisation, est susceptible de quitter l'organisation.

Pour cet exercice, nous allons réutilisés la connexion crée à l’exercice 2 du chapitre précédent. Nous allons créer un Dataset à partir de cette connexion. Les données sur les employés nécessaires pour prédire qui pourrait quitter notre organisation se trouvent déjà dans notre base de données Oracle

**Remarque** : pour exploiter pleinement les capacités de l'OML, le modèle d'apprentissage automatique et les données nécessaires pour faire une prédiction doivent tous deux se trouver dans la base de données Oracle

1.  Depuis l’Accueil, Cliquez sur Create puis choisissez Dataset

    ![](80404ed568639aeb3cf7b4c800d33a83.png)

2.  Sélectionnez la connection ‘orclpdb’, sélectionnez la table EMPLOYEE_DATA dans le schéma dmuser01, puis déposer la dans le panneau à droite de l’écran.

    ![](85dbf1b46ccb63c709bde87817466106.png) ![](e4d02a98f5320b13b5a9342ca9b1731b.png)

3.  Modifiez les colonnes Age et EmployeeNumber en attribut et sauvegardez le dataset avec le nom EMLOYEE_DATA.
4.  Retournez à l’accueil, et en haut à droite, cliquez sur les trois points verticaux pour ouvrir le menu déroulant, puis sélectionnez Register ML Model.

    !["registermlmodeloption"](a1452b933a84561f2426c3ad0a9a38d9.png)

5.  Sélectionnez la connexion orclpdb qui a été créée au début du chapitre.

    ![](efcbd5e83379cac703d0d828a1883e82.png)

6.  Maintenant, sélectionnez "*ATTRITION-MODEL-SVM*" dans la liste des modèles ML disponibles et cliquez sur Register en bas de la page.

    !["attritionmodelsvm"](9d9670c16bf172abe4b838b13cf04fbf.png)

7.  Depuis la page d'accueil, cliquez sur le bouton hamburger en haut à gauche, sélectionnez Machine Learning, et pour le modèle ATTRITION-MODEL-SVM que nous venons d'enregistrer, sélectionnez l'option Inspecter à l'aide des trois points verticaux qui apparaissent sur le côté droit du modèle.

    !["paneltoinspectattritionmodelsvm"](c50ed3ee9e0364a110671a305da302e7.png)

8.  Inspecter le modèle enregistré. Remarquez qu'il y a plus de métadonnées apparaissant sur les modèles OML hébergés dans la base de données Oracle que sur les modèles ML natifs hébergés dans Oracle Analytics Server. Cela montre que les modèles OML sont beaucoup plus sophistiqués. Parcourez les différents onglets (Général, Accès, Détails, Related). Remarquez que sous Détails - Colonnes de sortie, il y a une Prédiction et une PrédictionProbabilité qui nous diront qui est susceptible de partir ensuite. De même, l'onglet Related propose une série de métadonnées sous-jacentes stockées dans des vues DM\$ au sein de la base de données Oracle, contenant des détails importants sur la manière dont le modèle a été formé, testé et évalué

    !["relatedtabforinspectattritionmodelsvm"](2a889b76a7657b06e69265ec07b5635e.png)

9.  Notre modèle OML enregistré est maintenant prêt à être appelé par Oracle Analytics Server pour faire des prédictions concernant les employés qui sont susceptibles de quitter l'organisation. Pour appeler ce modèle OML enregistré, cliquez sur Create en haut à droite de la page, puis choisissez Data Flow.

    !["dataflowcreateicon"](846a94419fbf0ae31b138695f2d7a96a.png)

10. Le flux de données de création vous demandera quel(s) dataset(s) vous souhaitez utiliser. Tapez "EMP" dans la fenêtre de recherche, puis sélectionnez EMPLOYEE-DATA et Add pour introduire un dataset contenant des informations clés sur les employés restants qui travaillent encore pour notre organisation.

    !["eedatatablefromoracledb"](f1eeef2e2bd9b4d8a5c8d707ba203170.png)

11. Cliquez sur le signe + à droite du nœud EMPLOYEE_DATA que nous venons d'ajouter au dataflow et choisissez Apply Model au bas des éléments présentés.

    !["plusiconandapplymodelicon"](b5a6d36e926c9e6a52166ccf0159ffba.png)

12. Sélectionnez ATTRITION-MODEL-SVM que nous avons enregistré à l'étape 6 ci-dessus, puis cliquez sur OK.

    ![](ff0e84cd6b1e2e8cd3f107a5e3e1a00b.png)

13. Étant donné qu'un dataset similaire a été utilisé pour former et tester notre modèle, les sorties Prediction et PredictionProbability sont automatiquement mises en correspondance avec les colonnes d'entrée nécessaires à la création de nos prédictions.

    !["applymodelconfigpanel"](e71139511f71e5df309961a3d395c385.png)

14. Cliquez sur le signe + à droite du nœud Apply Model et choisissez Save Data

    !["plusiconandsavedataicon"](70817d0773a7d9de7518a3349dae7ea3.png)

15. Sauvegardez le nouveau dataset dans la base orclpdb avec le nom PRED_EMP_ATTRIT. Donnez ce nom également pour le dataset.

    ![](c3106d3393513ac00c2004fb709671c6.png)

16. Sauvegardez votre data flow en le nommant PRED-EMP-ATTRIT-OML puis, en utilisant la flèche en haut à droite de la page, exécutez l'ensemble de données pour créer les prédictions.

    !["savedataflowpanela"](d4fca3123709336fcee81ebf8eac1d4a.png)

17. Une fois le modèle appliqué quittez le data flow que vous venez de créer.
18. En utilisant l'icône hamburger en haut à gauche de la page, ouvrez le panneau DATA et entrez EMP pour voir tous les ensembles de données contenant "EMP" dans leur nom. Cliquez sur le dataset PRED-EMP-ATTRIT pour créer un nouveau workbook.

    !["predempatrittable"](c449bef822e5725d5caee5de27c65970.png)

19. Sélectionnez toutes les colonnes de l'ensemble de données, cliquez avec le bouton droit de la souris et sélectionnez Pick Visualization (Choisir la visualisation). Choisissez ensuite la visualisation Tableau pour afficher les prédictions.

    !["columnselectionpanel"](05c2fc500fb71e30ee88a1fac80cbbc9.png)

20. En utilisant la technique du glisser-déposer, réorganisez les colonnes de chaque ligne de manière à ce que Prediction, PredictionProbabilité et EmployeeNumber apparaissent sur le côté droit du tableau. Vous pouvez également déplacer des attributs clés tels que DEPARTMENT, JOBROLE, ... vers le côté droit.

    !["columnsrearrangedintable"](066cf1353d08cfec0dba7f9bb345bee0.png)

21. Cliquez sur l'attribut Prédiction et faites-le glisser vers la section Filtres en haut de la page, puis filtrez uniquement sur les salariés dont la prédiction est Oui, ce qui signifie qu'ils sont susceptibles de partir. Triez ensuite sur la base de "PredictionProbability" de haut en bas pour voir les employés qui ont le plus grand risque de partir.

    !["tablefilteredandsorted"](344f45cd58121247f691fa19b052a148.png)

22. Continuez à construire des visualisations qui, selon vous, pourraient aider à comprendre les prévisions d'attrition jusqu'à ce que vous obteniez un canevas intéressant.

    !["finalcanvas"](64e8727d030ef431c49ea04138355511.png)
