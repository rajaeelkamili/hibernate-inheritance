# TP 4 : Héritage avec Hibernate - Stratégies de Mapping

## Description
Ce projet illustre les trois stratégies d'héritage JPA/Hibernate :
- **SINGLE_TABLE** : une seule table pour toute la hiérarchie (ex. Véhicules)
- **JOINED** : une table par classe avec jointures (ex. Employés)
- **TABLE_PER_CLASS** : une table complète par classe concrète (ex. Produits)

## Prérequis
- JDK 8 ou supérieur
- Maven 3.x

## Structure du projet
```
hibernate-inheritance/
├── src/
│   └── main/
│       ├── java/com/example/
│       │   ├── App.java
│       │   └── model/
│       │       ├── singletable/   (Vehicule, Voiture, Moto)
│       │       ├── joined/        (Employe, Developpeur, Manager)
│       │       └── tableperclass/ (Produit, Livre, Electronique)
│       └── resources/META-INF/
│           └── persistence.xml
└── pom.xml
```

## Exécution

### Compiler le projet
```bash
mvn clean compile
```

### Lancer l'application
```bash
mvn exec:java -Dexec.mainClass="com.example.App"
```

### Ou en une seule commande
```bash
mvn clean compile exec:java -Dexec.mainClass="com.example.App"
```

## Résultats attendus
- Création des tables H2 en mémoire selon chaque stratégie
- Affichage des requêtes SQL générées par Hibernate
- Récupération polymorphique des entités via JPQL
