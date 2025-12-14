# school-bdg-microservices
Architecture microservices pour gestion scolaire avec Spring Boot, Eureka, Config Server et Docker


###################################### README   #########################

# 🎓 School Microservices Architecture

Architecture microservices pour la gestion d'un établissement scolaire avec Spring Boot, Eureka, Config Server et Docker.

## 🏗️ Architecture
```
                      Client/Frontend
                            ↓
                      API Gateway (8080)
                            ↓
                      Eureka Server (8761)
                      Config Server (8888)
                            ↓
        ┌──────────┬──────────┬──────────┬──────────┬──────────┐
        ↓          ↓          ↓          ↓          ↓          ↓
    Etudiant   Classe   Enseignant   Note     Matiere
    (8081)    (8082)     (8083)     (8084)    (8085)
```

## 📦 Microservices

| Service | Port | Description |
|---------|------|-------------|
| Eureka Server | 8761 | Service Discovery |
| Config Server | 8888 | Gestion centralisée des configurations |
| API Gateway | 8080 | Point d'entrée unique |
| Etudiant Service | 8081 | Gestion des étudiants |
| Classe Service | 8082 | Gestion des classes |
| Enseignant Service | 8083 | Gestion des enseignants |
| Note Service | 8084 | Gestion des notes |
| Matiere Service | 8085 | Gestion des matières |

## 🚀 Prérequis

- Java 17+
- Maven 3.8+
- Docker & Docker Compose
- Git

## ⚙️ Configuration

Les configurations sont centralisées dans un repository séparé :
```
https://github.com/DRADiallo/school-bdg-config-repo
```

## 🛠️ Installation

### 1. Cloner le projet
```bash
git clone https://github.com/DRADiallo/school-microservices.git
cd school-microservices
```

### 2. Compiler tous les services
```bash
# Compiler individuellement chaque service
cd eureka-server && mvn clean package -DskipTests && cd ..
cd config-server && mvn clean package -DskipTests && cd ..
cd api-gateway && mvn clean package -DskipTests && cd ..
cd etudiant-service && mvn clean package -DskipTests && cd ..
cd classe-service && mvn clean package -DskipTests && cd ..
cd enseignant-service && mvn clean package -DskipTests && cd ..
cd note-service && mvn clean package -DskipTests && cd ..
cd matiere-service && mvn clean package -DskipTests && cd ..
```

### 3. Lancer avec Docker
```bash
docker-compose up --build
```

### 4. Accéder aux services

- **Eureka Dashboard** : http://localhost:8761
- **Config Server** : http://localhost:8888
- **API Gateway** : http://localhost:8080
- **Etudiants** : http://localhost:8080/api/etudiants
- **Classes** : http://localhost:8080/api/classes
- **Enseignants** : http://localhost:8080/api/enseignants
- **Notes** : http://localhost:8080/api/notes
- **Matières** : http://localhost:8080/api/matieres

## 📝 API Endpoints

### Etudiant Service
- `GET /api/etudiants` - Liste tous les étudiants
- `GET /api/etudiants/{id}` - Récupérer un étudiant
- `POST /api/etudiants` - Créer un étudiant
- `PUT /api/etudiants/{id}` - Modifier un étudiant
- `DELETE /api/etudiants/{id}` - Supprimer un étudiant

### Classe Service
- `GET /api/classes` - Liste toutes les classes
- `GET /api/classes/{id}` - Récupérer une classe
- `POST /api/classes` - Créer une classe
- `PUT /api/classes/{id}` - Modifier une classe
- `DELETE /api/classes/{id}` - Supprimer une classe

*(Même structure pour les autres services)*

## 🤝 Contribution

1. Fork le projet
2. Créer une branche (`git checkout -b feature/nouvelle-fonctionnalite`)
3. Commit vos changements (`git commit -m 'Ajout nouvelle fonctionnalité'`)
4. Push vers la branche (`git push origin feature/nouvelle-fonctionnalite`)
5. Créer une Pull Request

## 👥 Équipe

- Votre nom - 	Abdoulaye GAYE
- Collaborateur Aliou Dicory BALDE
- Collaborateur Abdourahamane DIALLO

## 📄 Licence

Ce projet est sous licence MIT.
