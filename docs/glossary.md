# Glossary

| Term             | Definition                                                                                                                                  | Avoid                      |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|
| Member           | A person who borrows books from the library and signs in with a user account the librarian created for them.                               | Patron, Borrower, Customer |
| Librarian        | The person who manages the catalog and the members and sees all loans; a librarian has a user account but is no member and does not borrow. | Admin, Administrator       |
| User Account     | The username, password, and role a person signs in with; it holds no name or email address, which belong to the member.                     |                            |
| Role             | What a user account may do: either member or librarian.                                                                                      |                            |
| Catalog          | All books the library owns, as members and the librarian search them.                                                                        | Inventory, Stock           |
| Book             | A work in the catalog, identified by its ISBN and described by its title and author; the library may own several copies of it.               | Item, Volume               |
| Copy             | One physical specimen of a book; the copies of a book are interchangeable and are counted, not tracked one by one.                          | Exemplar                   |
| Available Copies | The number of copies of a book minus its active loans; a member can borrow the book while this number is greater than 0.                    |                            |
| Removed Book     | A book the librarian took out of the catalog; it no longer appears in a search and cannot be borrowed, but its loans stay in the loan history. | Deleted Book, Archived Book |
| Loan             | The record that a member borrowed one copy of a book, with the date and time it was borrowed and, once returned, the date and time of return. | Checkout, Rental, Lending  |
| Active Loan      | A loan whose book the member has not returned yet.                                                                                           | Outstanding Loan           |
| Loan History     | The returned loans of one member or of all members, with their borrow and return dates.                                                      |                            |
| Borrow           | The action of a member that starts a loan and lowers the available copies of the book by one.                                               | Check out, Rent            |
| Return           | The action of a member that ends an active loan and raises the available copies of the book by one.                                         | Check in                   |
