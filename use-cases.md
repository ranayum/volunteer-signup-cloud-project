# Use cases

Anyone can create an event made up of roles, which are made up of shifts. Anyone can also sign up for an open shift just by submitting a name; no account or sign-in is required. Signups are anonymous: the system stores whatever name is given but doesn't verify identity, so the same person can sign up more than once under different names.

An **event** has a name, description, date, and 1–10 roles. A **role** is a position within an event and has 1–50 shifts. Once an event is created, its roles and shifts are fixed and cannot be added, changed, or removed. Role and shift order is set at creation and stays the same everywhere they're shown (events list, role details).

---

## Browse Events

A user opens the application to see what events exist.

They see all events, newest first. Each entry shows the event's name, description, and date, followed by its roles and each role's remaining shifts. If no events exist, the list is empty.

Clicking a role opens the Role Details screen for that role. The Browse Events screen also has a way to create a new event.

### Scenarios

- **Empty list**: No events exist, so the list is empty, but the create-event option is still shown.
- **List with data**: Each entry shows the event's name, description, and date, followed by its roles and each role's remaining shifts.
- **Newest first**: With more than one event, the most recently created one appears first.
- **Open role details**: Clicking a role opens the Role Details screen for that role.
- **Create event**: Choosing "create event" opens the event creation flow.

---

## Create an Event

Someone wants to set up a new event for volunteers to sign up for.

They provide:

- a name (at most 100 characters)
- a description (at most 280 characters)
- a date
- between one and ten roles, each with a distinct label (at most 100 characters) and between one and fifty shifts

The system creates the event and returns them to the Browse Events screen, where the new event appears first, with each of its roles showing its count of available shifts.

If they cancel, they return to the Browse Events screen without creating anything.

If the input is invalid (specified further in the third scenario), creation fails and the user is told the input is invalid.

### Scenarios

- **Successful create**: Valid name, description, date, and roles. The system creates the event and returns to the Browse Events screen, where the new event appears first, with each role showing its count of available shifts.
- **Cancel**: They leave the create flow without submitting. They return to the Browse Events screen; no new event is created.
- **Invalid input**: If the name, description, or date is missing or too long, if there are fewer than one or more than ten roles, if any role label is missing, too long, or repeated, or if any role has fewer than one or more than fifty shifts, creation fails and the user is told the input is invalid.

---

## Role Details

Someone clicks a role from the Browse Events screen (or opens it directly) to see its shifts.

They see the role's label and its shifts in creation order. Each shift shows whether it is open or already taken, and if taken, the name of the volunteer signed up for it. Clicking an open shift takes them to the Signup screen for that shift.

If the role does not exist, they are told it was not found.

### Scenarios

- **Role details page**: For an existing role, they see its label and each shift, showing whether it's open or taken, and the volunteer's name for any taken shift.
- **Open shift click**: Clicking an open shift takes them to the Signup screen for that shift.
- **Unknown role**: The role id does not exist. They are told the role was not found.

---

## Sign Up for a Shift

Someone has an open shift selected and enters a name.

The system records that name against the shift. They then see the Role Details screen, where the shift now shows as taken with their name.

Signing up is anonymous: the system does not verify identity, so the same person may sign up for other shifts under different names.

If the shift does not exist, signup fails as not found. If the shift has already been taken by someone else, signup fails as unavailable. If the name is missing, blank, or longer than 100 characters, signup fails as invalid.

### Scenarios

- **Successful signup**: They enter a valid name for an open shift. The system records the signup and shows the Role Details screen with that shift now taken under their name.
- **Already taken**: Someone else signed up for the shift first. Signup fails as unavailable, and they're told so.
- **Unknown shift**: Signing up for a missing shift fails as not found.
- **Invalid input**: For example, a missing name. Signup does not proceed; they stay on the signup screen and see that the input is invalid.

---