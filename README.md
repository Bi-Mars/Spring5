# _Criminal Evidence Management System_
--- ---
## _Description about the project_
Criminal Evidence Management System is an application used to manage polic criminal evidence for various cases. It is just a Proof-of-Concept application and not a real application. This application serves as a benchmark to use a lot of what Spring has to offer.
--- --- 
## _Requirements_
1. A user should have secured account to access the application
2. **Types of Account**:
   1. **Viewer:**
      - The user can query the evidence database to retrieve information.
   2. **Detective:**
      - The user that can submit evidence, retrieve it for analysis, or return it to the evidence locker.
   3. **Admin:**
      - An account with special privileges that can manage other users’ activities on the evidence system.

3. Evidence has to be linked to a case.
4. A case usually has multiple evidence items linked to it.
5. Every time a piece of evidence is submitted, retrieved for analysis or returned, a track entry is created that contains the detective accessing the evidence and the reason for him/her to do so.
6. A detective can be a lead on a case investigation, but can also be an investigator for another case. Thus, a detective can work on multiple cases at once.
7. A detective can have different ranks.
    1. **TRAINEE:** 
        - No access to the evidence system
    2. **JUNIOR:** 
        - Read access to the evidence system
    3. **SENIOR:** 
        - Write access to the evidence system.
    4. **INSPECTOR:** 
        - Write access to the evidence system and read access to the personnel system.
    5. **CHIEF_INSPECTOR:** 
        - Write access to the evidence system and personnel system.
8. Cases can be classified based on their severity as follows.
    1. **INFRACTION:** 
        - The smallest of crimes, punishable with community service and/or a fine.
    2. **MISDEMEANOR:** 
        - A crime punishable with incarceration for one year or less.
    3. **FELONY:** 
        - The most serious crimes.
9. Cases can be classified by the investigation status as follows.
    1. **SUBMITTED:** 
        - Recently introduced into the system.
    2. **UNDER_INVESTIGATION:** 
        - The evidence is being collected; the investigation is in process.
    3. **IN_COURT:** 
        - All evidence is submitted, conclusions have been drawn, people have been arrested, and now the lawyers are doing their thing in court.
    4. **CLOSED:** 
        - All evidence is archived, the case has been solved; people have been sentenced.
    5. **DISMISSED:** 
        - An invalid case that required no investigation.
    6. **COLD:** 
        - A case that was in UNDER_INVESTIGATION state for more than 10 years.
10. When a case is closed, all evidence is archived.
11. Evidence is stored in different storage locations.

--- ---
### _Diagram with relationship between classes_

![Class Diagram](/imgForReadMe/class_diagram.png "Class Diagram")

**_About Class Diagram_**
- The classes that are wrapped in dark rectangle in above figure are entity classes and the entity classes map to tables in the database.
- The entities have common fields which are grouped in _AbstractEntity_ class to avoid having duplicated code.
    - These entities are used by hibernate to identify uniquely each entity instance (_id_) and fields used to audit each entity instance (_createdAt and modifiedAt_) and keep track of how many times an entity was modified (_version_)
--- ---
### _Database Structure and Foreign Keys_

![Database Structure and Foreign Keys](/imgForReadMe/database_structure_foreign_key.png "Database Structure and Foreign Keys")
--- ---

### _Application Architecture_ 
Criminal Evidence Management System was designed with Multitier architecture in mind.

![Multitier Application Architecture](/imgForReadMe/applicationArchitecture.jpg "Multitier Application Architecture")
--- ---
### _UML Diagram_ 
UML Diagram describes the general functionality of the application. The _Request Dispatcher_ and _Controller_ are part of the web tier

![UML Diagram](/imgForReadMe/uml.jpg "UML Diagram")
--- ---

### _Set-up_
1. **JDK**
    - JRE
    - JVM version 1.8 (Used) or above
2. **Build Tool**
    - Maven
    - Gradle (Used)
3. **IDE**
    - Eclipse
    - IntelliJ (Used)
4. **Spring Jars**
5. **Spring Boot initializer**
6. **Hibernate Jars**
7. **JPA Jars**
--- ---

##### _Reference_
1. **Pivotal Certified Professional Core Spring 5 Developer Exam: A Study Guide Using Spring Framework 5** - _luliana Cosmina_

--- --- 