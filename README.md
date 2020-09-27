# Idea

Take meteor's idea of the database on the client. What if the data is too large for the client? Then it gets more data on the backend.

The data lives in a store in Elm. It is reactive - that is it subscribes to updates on the backend.

- The backend streams updates to the frontend store
- The frontend store is normalized
- The frontend does map reduce on the data for each view
- Mutations are optimistic
- KV entries vs indexes

## Data structures

- Base data structure at `organization/entity/id`
- A way that creates indexes on fields in the data structure for mutations
- A way to get indexed data
- A way to get cumulated data
- A way to search for data - either in a lucene way or on the indexes with hydration
- A blob store
- A way to rebuild all indexes if need be
- A way to clear indexes
- A way to migrate data from one version to another.
  - Define the versions in the structs and when it is loaded, migrate the values
    from one version to anther; that way you are always using the latest version?
  - Or just a migration framework that iterates over all records and updates them one at a time
- async background job system that can do some heavy computations
- What about abstractions in the UI so that you can build a thousand screens?

## The idea

- Put and get stuff from client naivly and let it manage the data syncronization
- Including the files
