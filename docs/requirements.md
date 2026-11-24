# Requirements: Book Library

Requirements catalog derived from [vision.md](vision.md). Domain terms follow [glossary.md](glossary.md).

## Functional Requirements

| ID     | Title                     | User Story                                                                                                                                              | Priority | Status |
|--------|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|----------|--------|
| FR-001 | Member Sign-In            | As a member, I want to sign in with my user account so that every loan I make is tied to me.                                                             | High     | Open   |
| FR-002 | Librarian Sign-In         | As a librarian, I want to sign in with my own user account so that I can reach the librarian functions.                                                 | High     | Open   |
| FR-003 | Sign Out                  | As a member or librarian, I want to sign out so that the next person at the same computer cannot act under my user account.                            | Medium   | Open   |
| FR-004 | Initial Librarian Account | As a librarian, I want a first librarian user account to exist when the application starts for the first time so that I can sign in and set up the library. | High     | Open   |
| FR-005 | Search Catalog            | As a member, I want to search the catalog by title, author, or ISBN so that I can find a book without asking the librarian.                             | High     | Open   |
| FR-006 | See Available Copies      | As a member, I want to see the number of available copies of each book in the search result so that I know whether I can borrow it.                     | High     | Open   |
| FR-007 | Librarian Catalog Search  | As a librarian, I want to search the catalog by title, author, or ISBN so that I can answer a member's question about a book.                           | Medium   | Open   |
| FR-008 | Borrow Book               | As a member, I want to borrow a book that has an available copy so that I can take it home.                                                             | High     | Open   |
| FR-009 | Return Book               | As a member, I want to return a book I borrowed so that its copy becomes available to other members.                                                    | High     | Open   |
| FR-010 | My Active Loans           | As a member, I want to see my active loans so that I know which books I still have to return.                                                          | High     | Open   |
| FR-011 | My Loan History           | As a member, I want to see my returned loans with their borrow and return dates so that I can recall which books I have read.                           | Medium   | Open   |
| FR-012 | All Active Loans          | As a librarian, I want to see all active loans with member, book, and borrow date so that I know who has which book at any time.                        | High     | Open   |
| FR-013 | Full Loan History         | As a librarian, I want to see the returned loans of all members with their borrow and return dates so that I can tell who borrowed what and when.       | Medium   | Open   |
| FR-014 | Add Book                  | As a librarian, I want to add a book with its title, author, ISBN, and number of copies so that members can find and borrow it.                         | High     | Open   |
| FR-015 | Edit Book                 | As a librarian, I want to edit the title, author, ISBN, and number of copies of a book so that the catalog matches the shelf.                           | Medium   | Open   |
| FR-016 | Remove Book               | As a librarian, I want to remove a book from the catalog so that members no longer find a book the library no longer owns.                             | Medium   | Open   |
| FR-017 | Create Member Account     | As a librarian, I want to create a member with a name, email address, and user account so that the person can sign in and borrow books.                 | High     | Open   |
| FR-018 | Edit Member Details       | As a librarian, I want to edit a member's name and email address so that the member list stays correct.                                                 | Medium   | Open   |

## Non-Functional Requirements

| ID      | Title                    | Requirement                                                                                                                                                  | Category        | Priority | Status |
|---------|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|----------|--------|
| NFR-001 | Search Response Time     | 95% of catalog searches show their result within 1 second, with 10,000 books in the catalog.                                                                | Performance     | High     | Open   |
| NFR-002 | Loan Response Time       | 95% of borrow and return actions are confirmed to the member within 1 second.                                                                                | Performance     | High     | Open   |
| NFR-003 | Concurrent Users         | The system meets NFR-001 and NFR-002 with 50 signed-in users working at the same time.                                                                       | Scalability     | Medium   | Open   |
| NFR-004 | Catalog Size             | The system holds at least 10,000 books and 100,000 loans without violating NFR-001.                                                                          | Scalability     | Medium   | Open   |
| NFR-005 | Up-to-Date Active Loans  | A borrow or return confirmed to a member appears in the librarian's list of all active loans the next time the list is opened or refreshed, with no delay.  | Performance     | High     | Open   |
| NFR-006 | Borrowing Effort         | A signed-in member borrows a book in at most 3 interactions, starting from the catalog search result.                                                       | Usability       | Medium   | Open   |
| NFR-007 | Sign-In Required         | Every function except sign-in rejects a request without a signed-in user account; 0 functions are reachable anonymously.                                     | Security        | High     | Open   |
| NFR-008 | Librarian-Only Functions | 100% of librarian functions reject a signed-in member, and 100% of member functions reject a signed-in librarian, verified by automated tests for every view. | Security        | High     | Open   |
| NFR-009 | Password Storage         | Passwords are stored only as salted BCrypt hashes with a cost factor of at least 10; 0 passwords are stored in plain text.                                   | Security        | High     | Open   |
| NFR-010 | Package Rules            | The package rules of docs/architecture.md are checked by automated architecture tests on every build; a build with 1 or more violations fails.               | Maintainability | Medium   | Open   |

## Constraints

| ID    | Title                    | Constraint                                                                                                              | Category  | Priority | Status |
|-------|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------|----------|--------|
| C-001 | Runtime Platform         | The backend runs on Java 25.                                                                                            | Technical | High     | Open   |
| C-002 | Application Framework    | The application is built on Spring Boot 4.1.                                                                            | Technical | High     | Open   |
| C-003 | UI Framework             | The web interface is built with Vaadin Flow 25.                                                                         | Technical | High     | Open   |
| C-004 | Database Platform        | The system stores its data in PostgreSQL 18.                                                                            | Technical | High     | Open   |
| C-005 | Data Access              | The system accesses the database with jOOQ.                                                                             | Technical | High     | Open   |
| C-006 | Schema Migrations        | Every change to the database schema is a Flyway migration.                                                              | Technical | High     | Open   |
| C-007 | Authentication           | Sign-in uses Spring Security with username and password.                                                                | Technical | High     | Open   |
| C-008 | Browser Support          | The web interface supports the latest 2 versions of Chrome, Firefox, Safari, and Edge.                                  | Technical | Medium   | Open   |
| C-009 | No Payments or Fines     | The system handles no payments and no fines.                                                                            | Business  | High     | Open   |
| C-010 | No Reservations          | The system offers no reservations and no waiting lists for books.                                                       | Business  | High     | Open   |
| C-011 | Single Branch            | The system serves one library at one location; there is no support for several branches.                              | Business  | High     | Open   |
| C-012 | No Self-Service Sign-Up  | Only a librarian creates member accounts; a person cannot create their own user account.                                | Business  | High     | Open   |
| C-013 | No Password Reset        | The system offers no password reset in this version.                                                                    | Business  | Medium   | Open   |
| C-014 | No Social Sign-In        | The system offers no sign-in through a social network or an external identity provider in this version.               | Business  | Medium   | Open   |
| C-015 | No Due Date              | A loan has no due date; it stays active until the member returns the book.                                              | Business  | High     | Open   |
| C-016 | No Loan Limit            | The number of active loans a member may hold is limited only by the available copies, not by a maximum per member.      | Business  | Medium   | Open   |
