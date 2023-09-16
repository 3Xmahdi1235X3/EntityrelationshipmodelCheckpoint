Entities:

Gymnasium

Attributes: GymnasiumID (Primary Key), Name, Address, Telephone Number
Member

Attributes: MemberID (Primary Key), Last Name, First Name, Address, Date of Birth, Gender
Session

Attributes: SessionID (Primary Key), GymnasiumID (Foreign Key), Type of Sport, Schedule, Maximum Capacity
Coach

Attributes: CoachID (Primary Key), Last Name, First Name, Age, Specialty
Relationships:

A Member can register for multiple Sessions, and a Session can have multiple registered Members (Many-to-Many).
Each Session is associated with one Gymnasium (Many-to-One).
A Session can have multiple Coaches, and a Coach can lead multiple Sessions (Many-to-Many).

```



  +-----------------+        +-----------------+
  |    Gymnasium   |        |      Member     |
  +-----------------+        +-----------------+
  | GymnasiumID (PK)|        |   MemberID (PK) |
  |      Name       |        |   Last Name     |
  |    Address      |        |   First Name    |
  | Telephone Number|        |    Address      |
  +-----------------+        | Date of Birth   |
                             |     Gender      |
                             +-----------------+
                                       |
                                       |
                                       |
                                       |
                                       |
                            +-------------------+
                            |      Session      |
                            +-------------------+
                            | SessionID (PK)    |
                            | GymnasiumID (FK)  |
                            | Type of Sport     |
                            |     Schedule      |
                            | Maximum Capacity  |
                            +-------------------+
                                       |
                             /             |              \
                            /              |               \
                           /               |                \
                          /                |                 \
                         /                 |                  \
  +----------------+    +----------------+    +----------------+
  |     Coach      |    | CoachSession   |    | SessionMember |
  +----------------+    +----------------+    +----------------+
  | CoachID (PK)   |    | CoachSessionID  |    | SessionMemberID|
  | Last Name      |    | SessionID (FK)  |    | SessionID (FK) |
  | First Name     |    | CoachID (FK)    |    | MemberID (FK)  |
  | Age            |    +----------------+    +----------------+
  | Specialty      |
  +----------------+


  ```