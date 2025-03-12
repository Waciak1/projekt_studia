# projekt_studiaarticle-review-system/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── peerreview/
│   │   │           ├── Application.java
│   │   │           ├── config/
│   │   │           │   ├── SecurityConfig.java
│   │   │           │   └── WebConfig.java
│   │   │           ├── controller/
│   │   │           │   ├── ArticleController.java
│   │   │           │   ├── ReviewController.java
│   │   │           │   ├── RevisionRoundController.java
│   │   │           │   ├── DecisionController.java
│   │   │           │   └── UserController.java
│   │   │           ├── dto/
│   │   │           │   ├── ArticleDTO.java
│   │   │           │   ├── ReviewDTO.java
│   │   │           │   ├── RevisionRoundDTO.java
│   │   │           │   ├── DecisionDTO.java
│   │   │           │   └── UserDTO.java
│   │   │           ├── model/
│   │   │           │   ├── Article.java
│   │   │           │   ├── User.java
│   │   │           │   ├── Review.java
│   │   │           │   ├── RevisionRound.java
│   │   │           │   ├── Decision.java
│   │   │           │   └── enums/
│   │   │           │       ├── Role.java
│   │   │           │       ├── ArticleStatus.java
│   │   │           │       ├── ReviewStatus.java
│   │   │           │       ├── RevisionStatus.java
│   │   │           │       └── DecisionType.java
│   │   │           ├── repository/
│   │   │           │   ├── ArticleRepository.java
│   │   │           │   ├── UserRepository.java
│   │   │           │   ├── ReviewRepository.java
│   │   │           │   ├── RevisionRoundRepository.java
│   │   │           │   └── DecisionRepository.java
│   │   │           ├── service/
│   │   │           │   ├── ArticleService.java
│   │   │           │   ├── UserService.java
│   │   │           │   ├── ReviewService.java
│   │   │           │   ├── RevisionRoundService.java
│   │   │           │   ├── DecisionService.java
│   │   │           │   └── impl/
│   │   │           │       ├── ArticleServiceImpl.java
│   │   │           │       ├── UserServiceImpl.java
│   │   │           │       ├── ReviewServiceImpl.java
│   │   │           │       ├── RevisionRoundServiceImpl.java
│   │   │           │       └── DecisionServiceImpl.java
│   │   │           ├── exception/
│   │   │           │   ├── ResourceNotFoundException.java
│   │   │           │   ├── UnauthorizedException.java
│   │   │           │   └── GlobalExceptionHandler.java
│   │   │           └── util/
│   │   │               └── DateUtils.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── db/
│   │           └── migration/
│   │               ├── V1__Create_Users_Table.sql
│   │               ├── V2__Create_Articles_Table.sql
│   │               ├── V3__Create_Reviews_Table.sql
│   │               ├── V4__Create_RevisionRounds_Table.sql
│   │               └── V5__Create_Decisions_Table.sql
│   └── test/
│       └── java/
│           └── com/
│               └── peerreview/
│                   ├── controller/
│                   │   ├── ArticleControllerTests.java
│                   │   ├── ReviewControllerTests.java
│                   │   ├── RevisionRoundControllerTests.java
│                   │   ├── DecisionControllerTests.java
│                   │   └── UserControllerTests.java
│                   └── service/
│                       ├── ArticleServiceTests.java
│                       ├── UserServiceTests.java
│                       ├── ReviewServiceTests.java
│                       ├── RevisionRoundServiceTests.java
│                       └── DecisionServiceTests.java
├── pom.xml
├── .gitignore
├── Dockerfile
├── docker-compose.yml
└── README.md
