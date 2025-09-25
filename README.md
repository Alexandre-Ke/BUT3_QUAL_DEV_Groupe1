# BUT3_QUAL_DEV_Groupe1

# ASBank2023 - Application Bancaire IUT

[![Java](https://img.shields.io/badge/Java-11+-blue.svg)](https://www.java.com)
[![IntelliJ IDEA](https://img.shields.io/badge/IDE-IntelliJ%20IDEA-orange.svg)](https://www.jetbrains.com/idea/)
[![Tomcat](https://img.shields.io/badge/Server-Tomcat%209-green.svg)](https://tomcat.apache.org/)
[![MySQL](https://img.shields.io/badge/Database-MySQL%208-blue.svg)](https://www.mysql.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Description

Application bancaire développée dans le cadre du BUT3 Informatique - Module R5.A.08 Qualité Dev. 
Cette application web permet la gestion complète des opérations bancaires avec une architecture Java EE.

**Développé par :** Ouadie Abbaz, Arnaud Acquistapace, Alexandre Kesseler  
**Formation :** BUT3 QUAL_DEV_Groupe1  
**Année :** 2025

## 🚀 Fonctionnalités

- ✅ Gestion des comptes bancaires
- ✅ Opérations de transactions
- ✅ Interface web responsive
- ✅ Tests unitaires avec JUnit
- ✅ Architecture MVC avec Hibernate
- ✅ Sécurité des données

## 📦 Prérequis

### Configuration minimale
- **OS :** Windows 10/11, macOS 10.14+, ou Linux Ubuntu 20.04+
- **RAM :** 8 GB minimum (16 GB recommandé)
- **Espace disque :** 10 GB libre
- **Java JDK :** Version 11 ou supérieure
- **Connexion Internet :** Requise pour le téléchargement des dépendances

### Logiciels requis
| Logiciel | Version | Lien de téléchargement |
|----------|---------|------------------------|
| IntelliJ IDEA Ultimate | 2025.2.1 | [Télécharger](https://www.jetbrains.com/fr-fr/idea/) |
| Apache Tomcat | 9.0.109 | [Télécharger](https://tomcat.apache.org/) |
| MySQL Server | 8.0+ | [Télécharger](https://dev.mysql.com/downloads/mysql/) |
| MySQL Workbench | 8.0.43 | [Télécharger](https://dev.mysql.com/downloads/workbench/) |

## 🛠️ Installation

### 1️⃣ Installation d'IntelliJ IDEA Ultimate

1. Téléchargez IntelliJ IDEA Ultimate depuis [le site officiel](https://www.jetbrains.com/fr-fr/idea/)
2. Lancez l'installation avec le fichier `ideaIU-2025.2.1.exe`
3. Activez la licence étudiante :
   - Menu **Help** → **Manage Subscriptions** → **Activate**
   - Connectez-vous avec votre compte étudiant JetBrains

### 2️⃣ Récupération du projet

```bash
# Cloner le repository
git clone https://github.com/Alexandre-Ke/BUT3_QUAL_DEV_Groupe1.git

# Ou télécharger depuis Arche
# Cours : BUT3 – R5.A.08 – Qualité Dev
# Fichier : Code source.rar (Section 2)
```

Ouvrez le projet dans IntelliJ en sélectionnant le dossier `_00_ASBank2023`

### 3️⃣ Installation d'Apache Tomcat

1. Téléchargez [Tomcat 9](https://tomcat.apache.org/)
2. Extrayez l'archive dans un répertoire de votre choix
3. Dans IntelliJ, configurez Tomcat :
   - **Run** → **Edit Configurations**
   - Créez une nouvelle configuration Tomcat :
     - Name : `Tomcat 9.0.80`
     - Application server : Sélectionnez Tomcat 9.0.109
     - Port : `8080`
     - ✅ After launch
     - ✅ Show dialog

### 4️⃣ Installation de MySQL

#### Installation MySQL Server & Workbench

1. Téléchargez [MySQL Installer](https://dev.mysql.com/downloads/installer/)
2. Lancez l'installation et sélectionnez **MySQL Server 8.0.43**
3. Configuration :
   - Type : Development Computer
   - Port : `3306`
   - Définissez un mot de passe root
   - ✅ TCP/IP activé

#### Configuration de la base de données

1. Ouvrez MySQL Workbench
2. Créez une nouvelle connexion locale
3. Créez la base de données :

```sql
CREATE DATABASE Banque2023;
USE Banque2023;
```

4. Importez le script d'initialisation :
   - **File** → **Open SQL Script**
   - Sélectionnez `script/dumpSQL_JUnitTest.sql`
   - Exécutez le script

### 5️⃣ Configuration du projet

1. Modifiez le fichier `TestBanqueManager-context.xml` (ligne 42) :

```xml
<bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
    <property name="url" value="jdbc:mysql://localhost:3306/Banque2023"/>
    <property name="username" value="root"/>
    <property name="password" value="[votre_mot_de_passe]"/>
</bean>
```

2. Compilez le projet : **Build** → **Rebuild Project**

## ▶️ Exécution

### Lancement de l'application

1. Cliquez sur **Run** dans IntelliJ
2. Sélectionnez votre configuration Tomcat
3. L'application sera accessible à : `http://localhost:8080/_00_ASBank2023`

### Tests unitaires

Pour exécuter les tests :

```bash
# Dans IntelliJ
# Naviguez vers src/test/java/com/iut/banque/test/dao
# Clic droit sur TestsDaoHibernate → Run
```

✅ Tous les tests doivent passer avec succès

## 📁 Structure du projet

```
_00_ASBank2023/
├── 📁 .idea/                 # Configuration IntelliJ
├── 📁 Documentation/         # Documentation technique
│   └── Documentation Technique d'Installation - ASBank2025.pdf
├── 📁 script/               # Scripts SQL
│   ├── dumpSQL.sql
│   └── dumpSQL_JUnitTest.sql
├── 📁 src/                  # Code source
│   ├── 📁 main/
│   │   └── ...
│   └── 📁 test/            # Tests unitaires
│       ├── 📁 java/
│       │   └── 📁 com/iut/banque/test/
│       │       ├── 📁 dao/
│       │       │   └── TestsDaoHibernate.java
│       │       ├── 📁 facade/
│       │       └── 📁 modele/
│       └── 📁 resources/
│           ├── TestsBanqueManager-context.xml
│           └── TestsDaoHibernate-context.xml
├── 📁 WebContent/           # Ressources web
│   ├── 📁 js/
│   ├── 📁 JSP/
│   ├── 📁 style/
│   └── 📁 WEB-INF/
├── 📄 .gitignore
├── 📄 pom.xml              # Configuration Maven
├── 📄 README.md            # Ce fichier
└── 📄 RunSonar.bat         # Script SonarQube

```

## 🧪 Tests et Validation

### Points de vérification

- [x] IntelliJ IDEA Ultimate installé et activé
- [x] Tomcat 9 configuré dans IntelliJ
- [x] MySQL Server et Workbench installés
- [x] Base de données `Banque2023` créée
- [x] Script SQL importé avec succès
- [x] Configuration de connexion à la base de données
- [x] Compilation du projet réussie
- [x] Tests `TestsDaoHibernate` passés
- [x] Application accessible via navigateur

### Page d'accueil

Une fois l'installation terminée, vous devriez voir :

```
Bienvenue sur l'application IUT Bank 2023
     Information
     Page de Login
     
     Projet BUT-3A / 2023-2024
```

## Dépannage

### Problèmes courants

| Problème | Solution |
|----------|----------|
| **Port 8080 déjà utilisé** | Changez le port dans la configuration Tomcat (ex: 8081) |
| **Connexion MySQL échouée** | Vérifiez les identifiants dans `TestBanqueManager-context.xml` |
| **Tests échouent** | Assurez-vous que la base de données est créée et le script SQL exécuté |
| **Compilation échoue** | Invalidez les caches : **File** → **Invalidate Caches and Restart** |


## 👥 Contributeurs

- **Ouadie Abbaz** - Développeur
- **Arnaud Acquistapace** - Développeur  
- **Alexandre Kesseler** - Développeur

## 📚 Documentation

La documentation technique complète est disponible dans le dossier `/Documentation` :
- [Documentation Technique d'Installation - ASBank2025.pdf](Documentation/Documentation%20Technique%20d'Installation%20-%20ASBank2025.pdf)
