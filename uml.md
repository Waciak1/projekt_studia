classDiagram
    class Article {
        -Long id
        -String title
        -String abstract
        -String keywords
        -String fullText
        -Date submissionDate
        -ArticleStatus status
        -User author
        -List~Review~ reviews
        -List~RevisionRound~ revisionRounds
        +Long getId()
        +String getTitle()
        +void setTitle(String title)
        +String getAbstract()
        +void setAbstract(String abstract)
        +String getKeywords()
        +void setKeywords(String keywords)
        +String getFullText()
        +void setFullText(String fullText)
        +Date getSubmissionDate()
        +void setSubmissionDate(Date date)
        +ArticleStatus getStatus()
        +void setStatus(ArticleStatus status)
        +User getAuthor()
        +void setAuthor(User author)
        +List~Review~ getReviews()
        +void addReview(Review review)
        +List~RevisionRound~ getRevisionRounds()
        +void addRevisionRound(RevisionRound round)
    }

    class User {
        -Long id
        -String firstName
        -String lastName
        -String email
        -String password
        -List~Role~ roles
        -List~Article~ authoredArticles
        -List~Review~ assignedReviews
        +Long getId()
        +String getFirstName()
        +void setFirstName(String firstName)
        +String getLastName()
        +void setLastName(String lastName)
        +String getEmail()
        +void setEmail(String email)
        +String getPassword()
        +void setPassword(String password)
        +List~Role~ getRoles()
        +void addRole(Role role)
        +List~Article~ getAuthoredArticles()
        +List~Review~ getAssignedReviews()
    }

    class Review {
        -Long id
        -Article article
        -User reviewer
        -Integer score
        -String comments
        -String confidentialComments
        -ReviewStatus status
        -Date assignmentDate
        -Date completionDate
        -RevisionRound revisionRound
        +Long getId()
        +Article getArticle()
        +void setArticle(Article article)
        +User getReviewer()
        +void setReviewer(User reviewer)
        +Integer getScore()
        +void setScore(Integer score)
        +String getComments()
        +void setComments(String comments)
        +String getConfidentialComments()
        +void setConfidentialComments(String comments)
        +ReviewStatus getStatus()
        +void setStatus(ReviewStatus status)
        +Date getAssignmentDate()
        +void setAssignmentDate(Date date)
        +Date getCompletionDate()
        +void setCompletionDate(Date date)
        +RevisionRound getRevisionRound()
        +void setRevisionRound(RevisionRound round)
    }

    class RevisionRound {
        -Long id
        -Article article
        -Integer roundNumber
        -String editorComments
        -String authorResponse
        -Date startDate
        -Date responseDate
        -RevisionStatus status
        -List~Review~ reviews
        -Decision decision
        +Long getId()
        +Article getArticle()
        +void setArticle(Article article)
        +Integer getRoundNumber()
        +void setRoundNumber(Integer number)
        +String getEditorComments()
        +void setEditorComments(String comments)
        +String getAuthorResponse()
        +void setAuthorResponse(String response)
        +Date getStartDate()
        +void setStartDate(Date date)
        +Date getResponseDate()
        +void setResponseDate(Date date)
        +RevisionStatus getStatus()
        +void setStatus(RevisionStatus status)
        +List~Review~ getReviews()
        +void addReview(Review review)
        +Decision getDecision()
        +void setDecision(Decision decision)
    }

    class Decision {
        -Long id
        -DecisionType type
        -String comments
        -Date decisionDate
        -User editor
        -RevisionRound revisionRound
        +Long getId()
        +DecisionType getType()
        +void setType(DecisionType type)
        +String getComments()
        +void setComments(String comments)
        +Date getDecisionDate()
        +void setDecisionDate(Date date)
        +User getEditor()
        +void setEditor(User editor)
        +RevisionRound getRevisionRound()
        +void setRevisionRound(RevisionRound round)
    }

    class Role {
        <<Enumeration>>
        AUTHOR
        REVIEWER
        EDITOR
        ADMIN
    }

    class ArticleStatus {
        <<Enumeration>>
        DRAFT
        SUBMITTED
        UNDER_REVIEW
        AWAITING_REVISION
        REVISED
        ACCEPTED
        REJECTED
    }

    class ReviewStatus {
        <<Enumeration>>
        ASSIGNED
        IN_PROGRESS
        COMPLETED
        WITHDRAWN
    }

    class RevisionStatus {
        <<Enumeration>>
        AWAITING_REVIEWS
        REVIEWS_COMPLETED
        AWAITING_DECISION
        DECISION_MADE
        AWAITING_REVISION
        REVISED
    }

    class DecisionType {
        <<Enumeration>>
        ACCEPT
        MINOR_REVISION
        MAJOR_REVISION
        REJECT
    }

    Article "1" --> "*" Review
    Article "1" --> "*" RevisionRound
    Article "*" --> "1" User
    Review "*" --> "1" User
    Review "*" --> "1" RevisionRound
    RevisionRound "*" --> "1" Article
    RevisionRound "1" --> "0..1" Decision
    Decision "*" --> "1" User
    User "1" --> "*" Role
