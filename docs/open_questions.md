# Open Questions

Questions about the specification that the specification does not answer yet. A question is `Resolved` only when
the answer is in the specification itself; **Resolved in** names where. Resolved and withdrawn questions stay as
history.

## OQ-001: How fast must a borrow or return be confirmed?

**Element:** NFR-002  
**Raised by:** /requirements, 2026-11-23  
**Blocking:** No  
**Status:** Resolved  
**Assumed:** 95% of borrow and return actions are confirmed within 1 second, the same as the search threshold.  

The vision asks for quick borrowing and returning but names no number. The search threshold (NFR-001) was agreed
at 1 second; the catalog uses the same threshold for borrow and return.

**Answer:** Confirmed: 95% of borrow and return actions are confirmed within 1 second.  
**Answered by:** andypb, 2026-11-23  
**Resolved in:** NFR-002  

## OQ-002: What does "real time view of all loans" mean for the librarian?

**Element:** NFR-005  
**Raised by:** /requirements, 2026-11-23  
**Blocking:** No  
**Status:** Resolved  
**Assumed:** A borrow or return shows in the list of all active loans the next time the librarian opens or refreshes it; the open list does not update itself.  

Readings: (a) current on the next open or refresh; (b) an open list updates itself within a few seconds, without
a refresh (server push). Reading (b) adds push infrastructure to a system meant to stay small.

**Answer:** Confirmed: the list is current on the next open or refresh; no server push.  
**Answered by:** andypb, 2026-11-23  
**Resolved in:** NFR-005  

## OQ-003: How many interactions may borrowing take?

**Element:** NFR-006  
**Raised by:** /requirements, 2026-11-23  
**Blocking:** No  
**Status:** Open  
**Assumed:** At most 3 interactions, starting from the catalog search result.  

The vision's goal "make borrowing quick" needs a measurable threshold; 3 interactions allows select, borrow, and
confirm.

## OQ-004: How are passwords stored?

**Element:** NFR-009  
**Raised by:** /requirements, 2026-11-23  
**Blocking:** No  
**Status:** Open  
**Assumed:** Salted BCrypt hashes with a cost factor of at least 10, the Spring Security default.  

The vision requires known users but says nothing about password storage.

## OQ-005: Which browsers must the web interface support?

**Element:** C-008  
**Raised by:** /requirements, 2026-11-23  
**Blocking:** No  
**Status:** Resolved  
**Assumed:** The latest 2 versions of Chrome, Firefox, Safari, and Edge.  

The vision names no browsers. Libraries may run older school or community computers, which would need a wider range.

**Answer:** Confirmed: the latest 2 versions of Chrome, Firefox, Safari, and Edge.  
**Answered by:** andypb, 2026-11-23  
**Resolved in:** C-008  

## OQ-006: Are the copies of a book tracked one by one?

**Element:** Glossary: Copy  
**Raised by:** /requirements, 2026-11-23  
**Blocking:** No  
**Status:** Resolved  
**Assumed:** Copies are interchangeable and only counted; a loan names the book, not a specific copy.  

Readings: (a) a count of copies per book; (b) each copy has its own identifier (barcode, inventory number) and a
loan names the copy. Reading (b) lets the librarian tell which physical copy a member has.

**Answer:** Confirmed: copies are interchangeable and only counted; a loan names the book.  
**Answered by:** andypb, 2026-11-23  
**Resolved in:** Glossary: Copy  

## OQ-007: Which ISBN formats does the catalog accept?

**Element:** Entity: BOOK.isbn  
**Raised by:** /entity-model, 2026-11-23  
**Blocking:** No  
**Status:** Open  
**Assumed:** ISBN-10 or ISBN-13, stored as digits only without hyphens (an ISBN-10 may end in X); unique among books that are not removed, so a removed book can be added again.  

The glossary identifies a book by its ISBN but names no format. Readings: (a) ISBN-10 and ISBN-13 as entered;
(b) ISBN-13 only, an ISBN-10 converted on entry; (c) with check digit validation.

## OQ-008: How many copies of one book can the library own?

**Element:** Entity: BOOK.copies  
**Raised by:** /entity-model, 2026-11-23  
**Blocking:** No  
**Status:** Open  
**Assumed:** Between 1 and 999.  

The requirements name no limit. A school library may own a class set of 30; 999 leaves room without allowing typos
such as 10000.

## OQ-009: Must every member have a unique email address?

**Element:** Entity: MEMBER.email  
**Raised by:** /entity-model, 2026-11-23  
**Blocking:** No  
**Status:** Open  
**Assumed:** Required and unique.  

FR-017 lists the email address when creating a member. Children in a school library may have no email address, or
siblings may share a parent's address; either would need the address to be optional or not unique.
