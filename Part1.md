# Project Sprint 1

## Sprint Planning for Complex SQL Queries

### Objectives:

1. Master complex SQL queries including joins, subqueries, aggregate functions, and set operations.
2. Optionally explore SQL indexes to understand their impact on query performance.

### Success Criteria:

1. **Accuracy**: All queries should return the correct data as specified by test cases.
2. **Efficiency**: Queries should be optimized for performance, with execution times measured and documented.
3. **Complexity Handling**: Ability to handle multiple query operations like multiple joins and nested queries in a single statement.

### Deliverables:

1. Documentation of all SQL queries used, including explanations of how they work and why they were chosen for the task.

### Holistic Progress on Course-Level Competencies

**Competency: Problem Solving and Optimization**

**Progress**: Through the detailed analysis and optimization of SQL queries, demonstrate your ability to not only solve problems but also to optimize solutions for efficiency.

### Planning and Review Strategy

**Regular Reviews**: Schedule weekly review sessions with your team to assess progress against the success criteria and make necessary adjustments.

## Database Schema

### User Management

#### 1.1 Users
- **User_ID (PK)**: Unique identifier for each user.
- **Username**: User's chosen name.
- **Password**: Encrypted user password.
- **Email**: User's email address.
- **Role**: Distinguishes between regular users and admins.

#### 1.2 UserRole
- **Role_ID (PK)**: Unique identifier for each role.
- **Role_Name**: Name of the role (e.g., 'admin', 'user').

#### 1.3 Profile
- **Profile_ID (PK)**: Unique identifier for each profile.
- **User_ID (FK)**: Links to User.
- **Name**: User's full name.
- **Birthday**: User's date of birth.
- **Bio**: User's biography.

### Movie Management

#### 2.1 Movie
- **Movie_ID (PK)**: Unique identifier for each movie.
- **Title**: Name of the movie.
- **Release_Year**: Year the movie was released.
- **Duration**: Duration of the movie in minutes.
- **Director**: Director of the movie.
- **Description**: Brief description of the movie.

#### 2.2 Genre
- **Genre_ID (PK)**: Unique identifier for each genre.
- **Genre_Name**: Name of the genre.

#### 2.3 MovieGenre
- **Movie_ID (PK, FK)**: Links to Movie.
- **Genre_ID (PK, FK)**: Links to Genre.

### Rating and Review

#### 3.1 Rating
- **Rating_ID (PK)**: Unique identifier for each rating.
- **User_ID (FK)**: Links to User.
- **Movie_ID (FK)**: Links to Movie.
- **Rating**: Numeric rating given by the user.
- **Rating_Date**: Date when the rating was given.

#### 3.2 Review
- **Review_ID (PK)**: Unique identifier for each review.
- **User_ID (FK)**: Links to User.
- **Movie_ID (FK)**: Links to Movie.
- **Review_Text**: Textual review provided by the user.
- **Review_Date**: Date when the review was written.
- **Is_Bot**: Indicates if the review was made by a bot.

### Watchlist

#### 4.1 Watchlist
- **Watchlist_ID (PK)**: Unique identifier for each watchlist entry.
- **User_ID (FK)**: Links to User.
- **Movie_ID (FK)**: Links to Movie.

### Tag Management

#### 5.1 Tag
- **Tag_ID (PK)**: Unique identifier for each tag.
- **Tag_Name**: Name of the tag.

#### 5.2 MovieTag
- **Movie_ID (PK, FK)**: Links to Movie.
- **Tag_ID (PK, FK)**: Links to Tag.

### Relationship Explanations

**User to Movie through Rating and Review**
- **Description**: Users can rate and review multiple movies, and each movie can be rated and reviewed by multiple users. This is facilitated by the Rating and Review tables, which act as join tables between User and Movie.

**User to Genre through MovieGenre**
- **Description**: Users can explore movies by genre, and each movie can belong to multiple genres. This relationship is managed through the MovieGenre table, which links Movie and Genre.

**User to Movie through Watchlist**
- **Description**: Users can add multiple movies to their watchlist, and each movie can appear on the watchlists of multiple users. This is managed by the Watchlist table, which acts as a join table between User and Movie.

**User to Tag through MovieTag**
- **Description**: Users can view and filter movies by tags, and each movie can have multiple tags. This relationship is managed through the MovieTag table, which links Movie and Tag.

### Admin Permissions

**Special Consideration**: Users with the role of 'Admin' have additional permissions not available to regular users, such as managing user accounts or deleting reviews. This distinction is made using the UserRole table.
