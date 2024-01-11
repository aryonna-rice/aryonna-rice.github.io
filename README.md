# Aryonna Rice's Portfolio
## Table of Contents

1. [About Me](#about-me)
2. [What I Do Best](#what-i-do-best)
3. [Skills](#skills)
4. [Projects](#projects)
5. [Contact Information](#contact-information)

## About Me
Hi! I'm Aryonna, a passionate senior computer science student at the University of North Carolina at Chapel Hill with a flair for backend development. My expertise lies in crafting robust solutions using Python and Java. Proficient in SQL ORM, SQL CORE, and MS SQL, I delve into the intricacies of databases with ease. I am a problem solver and love a good challenge!

## What I Do Best
I thrive on problem-solving and enjoy the creative process of designing efficient solutions. Whether it's untangling complex coding challenges or engineering seamless backend systems, I'm in my element when transforming problems into elegant solutions.

## Skills
1. Python - Fluent
2. Java - Fluent
3. Lisp - Knowledgable
4. ML - Knowledgable
5. Prolog - Knowledgable
6. SQL – Knowledgeable
7. MS SQL – Knowledgeable
8. PostgreSQL – Knowledgeable
9. SQL ORM – Knowledgeable
10. Google Certified Associate Cloud Engineer
    
## Projects

## Saving Data to an MS SQL Database

### Task
Save data from a Pandas dataframe into a preexisting table in the company's MS SQL database in long and JSON format.

### Problem
Prior to my undertaking of the project, there was no interim table for data to be stored in one of the company's databases. The table my boss wanted me to create served as temporary storage for data (before it was saved to more specific tables). Overall, data from different dataframes would be saved in this table temporarily.

### Requirements / Criteria
- Remove all special characters and spaces from column names.
- Save data under new column names (col_name, col_val, data, etc).
- Dataframes with fewer than 1 million rows must all be inserted in under 60 seconds.

### Walk-through
The data to be inserted into the temporary table is originally held in a Pandas dataframe and looks something like this. The data would look like this in the long format table in the MS SQL database and would look like this if saved in the JSON format table.

### Skills Learned
- Setting up a connection with a database.
- Pandas:
  - to_sql, melt, pivot, merge, concat, etc.
- SQL:
  - Writing raw queries.
  - Injection attack-proof queries.
- Python code:
  - Created data-cleaning functions.
  - Utilized regular expressions.
  - Utilized concurrency (ThreadPoolExecutor) to insert data in batches.

### Results
#### Long Format
- Saved ~840,000 rows of data in 53.87 seconds.

#### JSON Format
- Saved ~11,800 rows of data in 12.34 seconds.

### Additional Achievements
- Team adopted my code into production.
- Offered a full-time position post-grad.

## Website Application for Computer Science Clubs at UNC

### Course
Web Development - COMP590

### Project Description
Design a website for Computer Science clubs at UNC for their use.

### My Role
- Worked on implementing APIs for seamless data communication.
- Utilized PostgreSQL for database management and integration.
- Developed application logic to ensure a smooth user experience.

### Results
- Promoted to tech lead based on the volume and quality of code produced.
- Received an A on the final project.
- Built strong connections with group members.

### Visuals

#### [Insert screenshot of the website's homepage here]
[Insert brief description or caption]

#### Tables I Created
<table>
  <tr>
   <td>
Name
   </td>
   <td>Description
   </td>
   <td>Attributes
   </td>
  </tr>
  <tr>
   <td><a href="https://github.com/comp423-23s/final-project-final-c3/blob/stage/backend/entities/club_entity.py" style="color:blue;">Club Entity</a></td>
   <td>There are many organizations that might be a part of the UNC XL. Each one needs to have the following information: an id (int), a club_code (int) used by leaders of the club, a name(str), a description (str) for users, a list of members (List[UserEntity]), and a list of leaders (List[UserEntity])
   </td>
   <td>id, club_code, name, description, members, leaders
   </td>
  </tr>
  <tr>
   <td>Event Entity
   </td>
   <td>Each event hosted by a club has its own entity. It has an id (int), a name (str), a description of the event (str), a location for the event (str), the date that it occurs (datetime), a club_id to match the event to the corresponding club (int), and a list of attendees (List[UserEntity])
   </td>
   <td>id, name, location, description, date, club_id, attendees
   </td>
  </tr>
  <tr>
   <td>Potential Club Entity
   </td>
   <td>Before a club can be declared an official club entity, it must be approved by an administrator. Thus, it remains as a ‘potential club entity’ until it is approved. These entities are composed of an id (int), a name (str), a description (str), and a founder_id (UserEntity) to represent who started the club. 
   </td>
   <td>id, name, description, founder_id
   </td>
  </tr>
  <tr>
   <td>Role Entity
   </td>
   <td>Each user of this application has a role. They may be a student, a leader (of a club), or an administrator. The attributes are: id (int), name (str), users (List[UserEntity]), permissions (List[PermissionEntity]0
   </td>
   <td>id, name, users, permissions
   </td>
  </tr>
  <tr>
   <td>User Entity
   </td>
   <td>Each user of this application has information that needs to be stored so that they can access different parts of the site. When signing in, one needs to fill out a ‘Profile’ form with the following information: First Name (str), Last Name (str), UNC email (str), and Pronouns (str). Then, each user has specific roles (List[RoleEntity]), permissions they are allowed (List[PermissionEntity]), clubs they are a part of (List[ClubEntity]), and clubs they are a leader of (List[ClubEntity]).
   </td>
   <td>id, pid, onyen, email, first_name, last_name, pronouns, roles, permissions, clubs, leading_clubs
   </td>
  </tr>
    <td>Category Entity
   </td>
   <td> Upon creation, each club has the option to be associated with certain tags or attributes. This makes the club able to be searched by a student when they search through clubs by filtering through them. The possible categories to choose from are: Black/African American, Asian American/Pacific Islander, Volunteer, Women, Hispanic/Latinx, LGBTQIA+, Video Games, Hackathon, Non-Binary, Volunteer, iOS Development, Business, and Project Management. The Category Entity has a list of clubs and Potential Clubs that have a specific Category ID. This information is stored in two different secondary tables, one for potential clubs and one for real clubs.
   </td>
   <td>id: Mapped[int] , name: Mapped[str], clubs: Mapped[list[ClubEntity]], potential_clubs: Mapped[list[PotentialClubEntity]]
   </td>
  </tr>
  <tr>
  <td>WeekDayTime Entity
   </td>
   <td> A WeekDayTime Entity is keeps track of the weekday (Monday, Tuesday, etc) and the time (4:00PM, 9:30 AM, ect) that a club meets. This entity was created because a standard datetime object wasn't applicable. The start and end times of an event are converted to strings in the from model method to work around issues with backend and front end time objects. Each WeekDayTime entity is associated with one singular Potential Club Entity or Club Entity.
   </td>
   <td>id: Mapped[int], day: Mapped[str], start_time: Mapped[time], end_time: Mapped[time]
   </td>
  </tr>
  <tr>
</table>

#### [Insert link to the application's GitHub repository]
[Insert additional context or details about the repository]

### Additional Achievements
- [Insert any other notable achievements or outcomes]




## Contact Information
- Email: aryonnarice@unc.edu
- LinkedIn: https://www.linkedin.com/in/aryonna-rice/

