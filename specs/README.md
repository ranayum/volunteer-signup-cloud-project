# Volunteer Signup Specs

This repo contains the specification for a volunteer signup app that allows users to create an event with roles, which themselves have shifts. Users can then sign up for shifts that are still available. We will deploy this application in a variety of ways using cloud technologies.

- [Use cases](use-cases.md) - Describes what users will experience with the running system.  These cases form the basis for acceptance tests.
- [API](openapi.yaml) - Describes the HTTP contract betwen the web brower (client) and the backend (server).
- [Data model](db.md) - Describes how data is stored in a DynamoDB table.
- [Sample data](sample-data.md) - Example data show in DynamoDB format.  These examples are codified in a machine-readable `[sample-data.json](sample-data.json)` format for seeding a database and/or use with tests.
- [UI mocks](ui/) This folder contains static HTML/CSS pages for the various views of the system.

