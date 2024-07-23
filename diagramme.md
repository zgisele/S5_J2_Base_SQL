<!--Diagramme MOOCademy-->

2.2.1. MOOCademy

Tables :

    Courses
        id (PK)
        title
        description

    Lessons
        id (PK)
        course_id (FK)
        title
        body

Relations :

    Un cours a plusieurs leçons 
<!--Diagramme The Pinterest-->
2.2.2. The Pinterest

Tables :

    Users
        id (PK)
        username
        email

    Pins
        id (PK)
        user_id (FK)
        image_url
        description (optional)

    Comments
        id (PK)
        user_id (FK)
        pin_id (FK)
        content

Relations :

    Un utilisateur peut créer plusieurs pins.
    Un utilisateur peut commenter plusieurs pins .
    Un pin peut avoir plusieurs commentaires .

<!--Diagramme The News-->
2.2.3. The News

Tables :

    Users
        id (PK)
        username
        email

    Links
        id (PK)
        user_id (FK)
        url
        title

    Comments
        id (PK)
        user_id (FK)
        link_id (FK)
        parent_comment_id (FK, nullable)
        content

Relations :

    Un utilisateur peut poster plusieurs liens .
    Un utilisateur peut commenter plusieurs liens.
    Un lien peut avoir plusieurs commentaires .
    Un commentaire peut avoir plusieurs réponses, mais une seule réponse peut avoir un parent .

<!--Diagramme Class-->

2.2.4. The Class

Tables :

    Students
        id (PK)
        name
        email

    Courses
        id (PK)
        title
        description

    Enrollments
        id (PK)
        student_id (FK)
        course_id (FK)

Relations :

    Un élève peut s'inscrire à un seul cours .
    Un cours peut avoir plusieurs élèves inscrits .