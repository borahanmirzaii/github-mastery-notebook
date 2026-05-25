# GitHub GraphQL API

> **Source root:** https://docs.github.com/en/graphql
> **Fetched:** 2026-05-26
> **Area:** 03 — GraphQL API

## Table of contents

- [GitHub GraphQL API documentation](#github-graphql-api-documentation)
- [About the GraphQL API](#about-the-graphql-api)
- [Introduction to GraphQL](#introduction-to-graphql)
- [Forming calls with GraphQL](#forming-calls-with-graphql)
- [Using GraphQL Clients](#using-graphql-clients) (formerly "Using the explorer" / "Explorer" — both redirect here; the GraphQL Explorer was removed Nov 11, 2025)
- [Rate limits and query limits for the GraphQL API](#rate-limits-and-query-limits-for-the-graphql-api) (formerly "Resource limitations")
- [Using pagination in the GraphQL API](#using-pagination-in-the-graphql-api)
- [Public schema](#public-schema)

---

## GitHub GraphQL API documentation

> Source: https://docs.github.com/en/graphql

To create integrations, retrieve data, and automate your workflows, use the GitHub GraphQL API. The GitHub GraphQL API offers more precise and flexible queries than the GitHub REST API.

### Recommended

* [About the GraphQL API](/en/graphql/overview/about-the-graphql-api)

  The GitHub GraphQL API offers flexibility and the ability to define precisely the data you want to fetch.

* [Introduction to GraphQL](/en/graphql/guides/introduction-to-graphql)

  Learn useful terminology and concepts for using the GitHub GraphQL API.

* [Forming calls with GraphQL](/en/graphql/guides/forming-calls-with-graphql)

  Learn how to authenticate to the GraphQL API, then learn how to create and run queries and mutations.

* [Using pagination in the GraphQL API](/en/graphql/guides/using-pagination-in-the-graphql-api)

  Learn how to traverse data sets using cursor based pagination with the GraphQL API.

* [Migrating from REST to GraphQL](/en/graphql/guides/migrating-from-rest-to-graphql)

  Learn best practices and considerations for migrating from GitHub's REST API to GitHub's GraphQL API.

* [Rate limits and query limits for the GraphQL API](/en/graphql/overview/rate-limits-and-query-limits-for-the-graphql-api)

  The GitHub GraphQL API has limitations in place to protect against excessive or abusive calls to GitHub's servers.

### Links

#### Getting started

* [About the GraphQL API](/en/graphql/overview/about-the-graphql-api)

  The GitHub GraphQL API offers flexibility and the ability to define precisely the data you want to fetch.

* [Forming calls with GraphQL](/en/graphql/guides/forming-calls-with-graphql)

  Learn how to authenticate to the GraphQL API, then learn how to create and run queries and mutations.

### Articles

* [About the GraphQL API](/en/graphql/overview/about-the-graphql-api)

  The GitHub GraphQL API offers flexibility and the ability to define precisely the data you want to fetch.

* [Public schema](/en/graphql/overview/public-schema)

  Download the public schema for the GitHub GraphQL API.

* [Breaking changes](/en/graphql/overview/breaking-changes)

  Learn about recent and upcoming breaking changes to the GitHub GraphQL API.

* [GraphQL changelog for 2026](/en/graphql/overview/changelog/2026)

  GraphQL schema changes from 2026.

* [GraphQL changelog for 2025](/en/graphql/overview/changelog/2025)

  GraphQL schema changes from 2025.

* [GraphQL changelog for 2024](/en/graphql/overview/changelog/2024)

  GraphQL schema changes from 2024.

* [GraphQL changelog for 2023](/en/graphql/overview/changelog/2023)

  GraphQL schema changes from 2023.

* [GraphQL changelog for 2022](/en/graphql/overview/changelog/2022)

  GraphQL schema changes from 2022.

* [GraphQL changelog for 2021](/en/graphql/overview/changelog/2021)

  GraphQL schema changes from 2021.

* [GraphQL changelog for 2020](/en/graphql/overview/changelog/2020)

  GraphQL schema changes from 2020.

* [GraphQL changelog for 2019](/en/graphql/overview/changelog/2019)

  GraphQL schema changes from 2019.

* [GraphQL changelog for 2018](/en/graphql/overview/changelog/2018)

  GraphQL schema changes from 2018.

* [GraphQL changelog for 2017](/en/graphql/overview/changelog/2017)

  GraphQL schema changes from 2017.

* [Rate limits and query limits for the GraphQL API](/en/graphql/overview/rate-limits-and-query-limits-for-the-graphql-api)

  The GitHub GraphQL API has limitations in place to protect against excessive or abusive calls to GitHub's servers.

* [Queries](/en/graphql/reference/queries)

  The query type defines GraphQL operations that retrieve data from the server.

* [Mutations](/en/graphql/reference/mutations)

  The mutation type defines GraphQL operations that change data on the server.

* [Objects](/en/graphql/reference/objects)

  Objects in GraphQL represent the resources you can access.

* [Interfaces](/en/graphql/reference/interfaces)

  Interfaces serve as parent objects from which other objects can inherit.

* [Enums](/en/graphql/reference/enums)

  Enums represent possible sets of values for a field.

* [Unions](/en/graphql/reference/unions)

  A union is a type of object representing many objects.

* [Input objects](/en/graphql/reference/input-objects)

  Input objects can be described as "composable objects" because they include a set of input fields that define the object.

* [Scalars](/en/graphql/reference/scalars)

  Scalars are primitive values Int, Float, String, Boolean, or ID.

* [Introduction to GraphQL](/en/graphql/guides/introduction-to-graphql)

  Learn useful terminology and concepts for using the GitHub GraphQL API.

* [Forming calls with GraphQL](/en/graphql/guides/forming-calls-with-graphql)

  Learn how to authenticate to the GraphQL API, then learn how to create and run queries and mutations.

* [Using global node IDs](/en/graphql/guides/using-global-node-ids)

  You can get global node IDs of objects via the REST API and use them in GraphQL operations.

* [Migrating from REST to GraphQL](/en/graphql/guides/migrating-from-rest-to-graphql)

  Learn best practices and considerations for migrating from GitHub's REST API to GitHub's GraphQL API.

* [Using GraphQL Clients](/en/graphql/guides/using-graphql-clients)

  You can run queries on real GitHub data using various GraphQL clients and libraries.

* [Using pagination in the GraphQL API](/en/graphql/guides/using-pagination-in-the-graphql-api)

  Learn how to traverse data sets using cursor based pagination with the GraphQL API.

* [Managing enterprise accounts](/en/managing-enterprise-accounts)

  You can manage your enterprise account and the organizations it owns with the GraphQL API.

* [Using the GraphQL API for Discussions](/en/graphql/guides/using-the-graphql-api-for-discussions)

  Learn how to use the GitHub Discussions GraphQL API.

* [Migrating GraphQL global node IDs](/en/graphql/guides/migrating-graphql-global-node-ids)

  Learn about the two global node ID formats and how to migrate from the legacy format to the new format.

---

## About the GraphQL API

> Source: https://docs.github.com/en/graphql/overview/about-the-graphql-api

The GitHub GraphQL API offers flexibility and the ability to define precisely the data you want to fetch.

### Overview

Here are some quick links to get you up and running with the GraphQL API:

* [Authentication](/en/graphql/guides/forming-calls-with-graphql#authenticating-with-graphql)
* [Root endpoint](/en/graphql/guides/forming-calls-with-graphql#the-graphql-endpoint)
* [Schema introspection](/en/graphql/guides/introduction-to-graphql#discovering-the-graphql-api)
* [Rate limits](/en/graphql/overview/resource-limitations)
* [Migrating from REST](/en/graphql/guides/migrating-from-rest-to-graphql)

For more information about GitHub's APIs, see [Comparing GitHub's REST API and GraphQL API](/en/rest/overview/about-githubs-apis).

### About GraphQL

The [GraphQL](https://graphql.org/) data query language is:

* **A [specification](https://spec.graphql.org/June2018/).** The spec determines the validity of the [schema](/en/graphql/guides/introduction-to-graphql#schema) on the API server. The schema determines the validity of client calls.

* **[Strongly typed](#about-the-graphql-schema-reference).** The schema defines an API's type system and all object relationships.

* **[Introspective](/en/graphql/guides/introduction-to-graphql#discovering-the-graphql-api).** A client can query the schema for details about the schema.

* **[Hierarchical](/en/graphql/guides/forming-calls-with-graphql).** The shape of a GraphQL call mirrors the shape of the JSON data it returns. [Nested fields](/en/graphql/guides/migrating-from-rest-to-graphql#example-nesting) let you query for and receive only the data you specify in a single round trip.

* **An application layer.** GraphQL is not a storage model or a database query language. The *graph* refers to graph structures defined in the schema, where [nodes](/en/graphql/guides/introduction-to-graphql#node) define objects and [edges](/en/graphql/guides/introduction-to-graphql#edge) define relationships between objects. The API traverses and returns application data based on the schema definitions, independent of how the data is stored.

### Why GitHub is using GraphQL

GitHub chose GraphQL because it offers significantly more flexibility for our integrators. The ability to define precisely the data you want—and *only* the data you want—is a powerful advantage over traditional REST API endpoints. GraphQL lets you replace multiple REST requests with *a single call* to fetch the data you specify.

For more details about why GitHub invested in GraphQL, see the original [announcement blog post](https://github.blog/2016-09-14-the-github-graphql-api/).

### About the GraphQL schema reference

The docs in the sidebar are generated from the GitHub GraphQL [schema](/en/graphql/guides/introduction-to-graphql#discovering-the-graphql-api). All calls are validated and executed against the schema. Use these docs to find out what data you can call:

* Allowed operations: [queries](/en/graphql/reference/queries) and [mutations](/en/graphql/reference/mutations).

* Schema-defined types: [scalars](/en/graphql/reference/scalars), [objects](/en/graphql/reference/objects), [enums](/en/graphql/reference/enums), [interfaces](/en/graphql/reference/interfaces), [unions](/en/graphql/reference/unions), and [input objects](/en/graphql/reference/input-objects).

For other information, such as authentication and rate limit details, check out the [guides](/en/graphql/guides).

### Requesting support

For questions, bug reports, and discussions about GitHub Apps, OAuth apps, and API development, explore the [API and Webhooks category in GitHub's Community Discussions](https://github.com/orgs/community/discussions/categories/api-and-webhooks). The discussions are moderated and maintained by GitHub staff, and answered by the GitHub community.

Consider reaching out to [GitHub Support](https://support.github.com/) directly using the contact form for:

* Guaranteed response from GitHub staff
* Support requests involving sensitive data or private concerns
* Feature requests
* Feedback about GitHub products

If you observe unexpected failures, you can use [githubstatus.com](https://www.githubstatus.com/) or the [GitHub status API](https://www.githubstatus.com/api) to check for incidents affecting the API.

---

## Introduction to GraphQL

> Source: https://docs.github.com/en/graphql/guides/introduction-to-graphql

Learn useful terminology and concepts for using the GitHub GraphQL API.

### GraphQL terminology

The GitHub GraphQL API represents an architectural and conceptual shift from the GitHub REST API. You will likely encounter some new terminology in the GraphQL API reference docs.

### Schema

A schema defines a GraphQL API's type system. It describes the complete set of possible data (objects, fields, relationships, everything) that a client can access. Calls from the client are validated and executed against the schema. A client can find information about the schema via introspection. A schema resides on the GraphQL API server. For more information, see Discovering the GraphQL API.

### Field

A field is a unit of data you can retrieve from an object. As the official GraphQL documentation explains, "The GraphQL query language is basically about selecting fields on objects."

According to the specification, "All GraphQL operations must specify their selections down to fields which return scalar values to ensure an unambiguously shaped response."

This means that if you try to return a field that is not a scalar, schema validation will throw an error. You must add nested subfields until all fields return scalars.

### Argument

An argument is a set of key-value pairs attached to a specific field. Some fields require an argument. Mutations require an input object as an argument.

### Implementation

A GraphQL schema may use the term *implements* to define how an object inherits from an interface.

Here's a contrived example of a schema that defines interface `X` and object `Y`:

```graphql
interface X {
  some_field: String!
  other_field: String!
}

type Y implements X {
  some_field: String!
  other_field: String!
  new_field: String!
}
```

This means object `Y` requires the same fields/arguments/return types that interface `X` does, while adding new fields specific to object `Y`. (The `!` means the field is required.)

In the reference docs, you'll find that:

* Each object lists the interface(s) *from which it inherits* under **Implements**.

* Each interface lists the objects *that inherit from it* under **Implementations**.

### Connection

Connections let you query related objects as part of the same call. With connections, you can use a single GraphQL call where you would have to use multiple calls to a REST API. For more information, see Migrating from REST to GraphQL.

It's helpful to picture a graph: dots connected by lines. The dots are nodes, the lines are edges. A connection defines a relationship between nodes.

### Edge

Edges represent connections between nodes. When you query a connection, you traverse its edges to get to its nodes. Every `edges` field has a `node` field and a `cursor` field. Cursors are used for pagination. For more information, see Using pagination in the GraphQL API.

### Node

*Node* is a generic term for an object. You can look up a node directly, or you can access related nodes via a connection. If you specify a `node` that does not return a scalar, you must include subfields until all fields return scalars. For information on accessing node IDs via the REST API and using them in GraphQL queries, see Using global node IDs.

### Discovering the GraphQL API

GraphQL is introspective. This means you can query a GraphQL schema for details about itself.

* Query `__schema` to list all types defined in the schema and get details about each:

  ```graphql
  query {
    __schema {
      types {
        name
        kind
        description
        fields {
          name
        }
      }
    }
  }
  ```

* Query `__type` to get details about any type:

  ```graphql
  query {
    __type(name: "Repository") {
      name
      kind
      description
      fields {
        name
      }
    }
  }
  ```

* You can also run an *introspection query* of the schema via a `GET` request:

  ```shell
  curl -H "Authorization: bearer TOKEN" https://api.github.com/graphql
  ```

  > **Note:** If you get the response `"message": "Bad credentials"` or `401 Unauthorized`, check that you are using a valid token. If you receive a `403` error with `Resource not accessible by personal access token`, ensure that your fine-grained personal access token is targeted to the correct resource owner. For example, it must target the organization that owns the repository you are trying to access.

  The results are in JSON, so we recommend pretty-printing them for easier reading and searching. You can use a command-line tool like [jq](https://stedolan.github.io/jq/) or pipe the results into `python -m json.tool` for this purpose.

  Alternatively, you can pass the `idl` media type to return the results in IDL format, which is a condensed version of the schema:

  ```shell
  $ curl -H "Authorization: bearer TOKEN" -H "Accept: application/vnd.github.v4.idl" \
  https://api.github.com/graphql
  ```

  > **Note:** The introspection query is probably the only `GET` request you'll run in GraphQL. If you're passing a body, the GraphQL request method is `POST`, whether it's a query or a mutation.

  For more information about performing queries, see Forming calls with GraphQL.

---

## Forming calls with GraphQL

> Source: https://docs.github.com/en/graphql/guides/forming-calls-with-graphql

### Authenticating with GraphQL

You can authenticate to the GraphQL API using a personal access token, GitHub App, or OAuth app.

#### Authenticating with a personal access token

To authenticate with a personal access token, follow the steps in Managing your personal access tokens. The data that you are requesting will dictate which scopes or permissions you will need.

For example, select the "issues:read" permission to read all of the issues in the repositories your token has access to.

All fine-grained personal access tokens include read access to public repositories. To access public repositories with a personal access token (classic), select the "public_repo" scope.

If your token does not have the required scopes or permissions to access a resource, the API will return an error message that states the scopes or permissions your token needs.

#### Authenticating with a GitHub App

If you want to use the API on behalf of an organization or another user, GitHub recommends that you use a GitHub App. In order to attribute activity to your app, you can make your app authenticate as an app installation. In order to attribute app activity to a user, you can make your app authenticate on behalf of a user. In both cases, you will generate a token that you can use to authenticate to the GraphQL API. For more information, see Registering a GitHub App and About authentication with a GitHub App.

#### Authenticating with an OAuth app

To authenticate with an OAuth token from an OAuth app, you must first authorize your OAuth app using either a web application flow or device flow. Then, you can use the access token that you received to access the API. For more information, see Creating an OAuth app and Authorizing OAuth apps.

### The GraphQL endpoint

The REST API has numerous endpoints. With the GraphQL API, the endpoint remains constant, no matter what operation you perform. For GitHub.com, that endpoint is:

```
https://api.github.com/graphql
```

### Communicating with GraphQL

Because GraphQL operations consist of multiline JSON, GitHub recommends using GraphQL Clients to make GraphQL calls. You can also use `curl` or any other HTTP-speaking library.

In REST, HTTP verbs determine the operation performed. In GraphQL, you'll provide a JSON-encoded body whether you're performing a query or a mutation, so the HTTP verb is `POST`. The exception is an introspection query, which is a simple `GET` to the endpoint. For more information on GraphQL versus REST, see Migrating from REST to GraphQL.

To query GraphQL in a `curl` command, make a `POST` request with a JSON payload. The payload must contain a string called `query`:

```shell
curl -H "Authorization: bearer TOKEN" -X POST -d " \
 { \
   \"query\": \"query { viewer { login }}\" \
 } \
" https://api.github.com/graphql
```

> [!NOTE]
> The string value of `"query"` must escape newline characters or the schema will not parse it correctly. For the `POST` body, use outer double quotes and escaped inner double quotes.

### About query and mutation operations

The two types of allowed operations in GitHub's GraphQL API are *queries* and *mutations*. Comparing GraphQL to REST, queries operate like `GET` requests, while mutations operate like `POST`/`PATCH`/`DELETE`. The mutation name determines which modification is executed.

For information about rate limiting, see Rate limits and query limits for the GraphQL API.

Queries and mutations share similar forms, with some important differences.

#### About queries

GraphQL queries return only the data you specify. To form a query, you must specify fields within fields (also known as *nested subfields*) until you return only scalars.

Queries are structured like this:

```
query {
  JSON-OBJECT-TO-RETURN
}
```

For a real-world example, see Example query.

#### About mutations

To form a mutation, you must specify three things:

1. *Mutation name*. The type of modification you want to perform.
2. *Input object*. The data you want to send to the server, composed of *input fields*. Pass it as an argument to the mutation name.
3. *Payload object*. The data you want to return from the server, composed of *return fields*. Pass it as the body of the mutation name.

Mutations are structured like this:

```
mutation {
  MUTATION-NAME(input: {MUTATION-NAME-INPUT!}) {
    MUTATION-NAME-PAYLOAD
  }
}
```

The input object in this example is `MutationNameInput`, and the payload object is `MutationNamePayload`.

In the mutations reference, the listed *input fields* are what you pass as the input object. The listed *return fields* are what you pass as the payload object.

For a real-world example, see Example mutation.

### Working with variables

Variables can make queries more dynamic and powerful, and they can reduce complexity when passing mutation input objects.

Here's an example query with a single variable:

```graphql
query($number_of_repos:Int!) {
  viewer {
    name
     repositories(last: $number_of_repos) {
       nodes {
         name
       }
     }
   }
}
variables {
   "number_of_repos": 3
}
```

There are three steps to using variables:

1. Define the variable outside the operation in a `variables` object:

```graphql
variables {
   "number_of_repos": 3
}
```

The object must be valid JSON. This example shows a simple `Int` variable type, but it's possible to define more complex variable types, such as input objects. You can also define multiple variables here.

2. Pass the variable to the operation as an argument:

```graphql
query($number_of_repos:Int!){
```

The argument is a key-value pair, where the key is the *name* starting with `$` (e.g., `$number_of_repos`), and the value is the *type* (e.g., `Int`). Add a `!` to indicate whether the type is required. If you've defined multiple variables, include them here as multiple arguments.

3. Use the variable within the operation:

```graphql
repositories(last: $number_of_repos) {
```

In this example, we substitute the variable for the number of repositories to retrieve. We specify a type in step 2 because GraphQL enforces strong typing.

This process makes the query argument dynamic. We can now simply change the value in the `variables` object and keep the rest of the query the same.

Using variables as arguments lets you dynamically update values in the `variables` object without changing the query.

### Example query

Let's walk through a more complex query and put this information in context.

The following query looks up the `octocat/Hello-World` repository, finds the 20 most recent closed issues, and returns each issue's title, URL, and first 5 labels:

```graphql
query {
  repository(owner:"octocat", name:"Hello-World") {
    issues(last:20, states:CLOSED) {
      edges {
        node {
          title
          url
          labels(first:5) {
            edges {
              node {
                name
              }
            }
          }
        }
      }
    }
  }
}
```

Looking at the composition line by line:

* `query {`

  Because we want to read data from the server, not modify it, `query` is the root operation. (If you don't specify an operation, `query` is also the default.)

* `repository(owner:"octocat", name:"Hello-World") {`

  To begin the query, we want to find a repository object. The schema validation indicates this object requires an `owner` and a `name` argument.

* `issues(last:20, states:CLOSED) {`

  To account for all issues in the repository, we call the `issues` object. (We *could* query a single `issue` on a `repository`, but that would require us to know the number of the issue we want to return and provide it as an argument.)

  Some details about the `issues` object:

  * The docs tell us this object has the type `IssueConnection`.
  * Schema validation indicates this object requires a `last` or `first` number of results as an argument, so we provide `20`.
  * The docs also tell us this object accepts a `states` argument, which is an `IssueState` enum that accepts `OPEN` or `CLOSED` values. To find only closed issues, we give the `states` key a value of `CLOSED`.

* `edges {`

  We know `issues` is a connection because it has the `IssueConnection` type. To retrieve data about individual issues, we have to access the node via `edges`.

* `node {`

  Here we retrieve the node at the end of the edge. The `IssueConnection` docs indicate the node at the end of the `IssueConnection` type is an `Issue` object.

* Now that we know we're retrieving an `Issue` object, we can look at the docs and specify the fields we want to return:

```graphql
title
url
labels(first:5) {
  edges {
    node {
      name
    }
  }
}
```

Here we specify the `title`, `url`, and `labels` fields of the `Issue` object.

The `labels` field has the type `LabelConnection`. As with the `issues` object, because `labels` is a connection, we must travel its edges to a connected node: the `label` object. At the node, we can specify the `label` object fields we want to return, in this case, `name`.

You may notice that running this query on the Octocat's public `Hello-World` repository won't return many labels. Try running it on one of your own repositories that does use labels, and you'll likely see a difference.

### Example mutation

Mutations often require information that you can only find out by performing a query first. This example shows two operations:

1. A query to get an issue ID.
2. A mutation to add an emoji reaction to the issue.

```graphql
query FindIssueID {
  repository(owner:"octocat", name:"Hello-World") {
    issue(number:349) {
      id
    }
  }
}

mutation AddReactionToIssue {
  addReaction(input:{subjectId:"MDU6SXNzdWUyMzEzOTE1NTE=",content:HOORAY}) {
    reaction {
      content
    }
    subject {
      id
    }
  }
}
```

Let's walk through the example. The task sounds simple: add an emoji reaction to an issue.

So how do we know to begin with a query? We don't, yet.

Because we want to modify data on the server (attach an emoji to an issue), we begin by searching the schema for a helpful mutation. The reference docs show the `addReaction` mutation, with this description: "Adds a reaction to a subject." Perfect!

The docs for the mutation list three input fields:

* `clientMutationId` (`String`)
* `subjectId` (`ID!`)
* `content` (`ReactionContent!`)

The `!`s indicate that `subjectId` and `content` are required fields. A required `content` makes sense: we want to add a reaction, so we'll need to specify which emoji to use.

But why is `subjectId` required? It's because the `subjectId` is the only way to identify *which* issue in *which* repository to react to.

This is why we start this example with a query: to get the `ID`.

Let's examine the query line by line:

* `query FindIssueID {`

  Here we're performing a query, and we name it `FindIssueID`. Note that naming a query is optional; we give it a name here so that we can include it in same GUI client window as the mutation.

* `repository(owner:"octocat", name:"Hello-World") {`

  We specify the repository by querying the `repository` object and passing `owner` and `name` arguments.

* `issue(number:349) {`

  We specify the issue to react to by querying the `issue` object and passing a `number` argument.

* `id`

  This is where we retrieve the `id` of `https://github.com/octocat/Hello-World/issues/349` to pass as the `subjectId`.

When we run the query, we get the `id`: `MDU6SXNzdWUyMzEzOTE1NTE=`

> [!NOTE]
> The `id` returned in the query is the value we'll pass as the `subjectID` in the mutation. Neither the docs nor schema introspection will indicate this relationship; you'll need to understand the concepts behind the names to figure this out.

With the ID known, we can proceed with the mutation:

* `mutation AddReactionToIssue {`

  Here we're performing a mutation, and we name it `AddReactionToIssue`. As with queries, naming a mutation is optional; we give it a name here so we can include it in the same GUI client window as the query.

* `addReaction(input:{subjectId:"MDU6SXNzdWUyMzEzOTE1NTE=",content:HOORAY}) {`

  Let's examine this line:

  * `addReaction` is the name of the mutation.
  * `input` is the required argument key. This will always be `input` for a mutation.
  * `{subjectId:"MDU6SXNzdWUyMzEzOTE1NTE=",content:HOORAY}` is the required argument value. This will always be an input object (hence the curly braces) composed of input fields (`subjectId` and `content` in this case) for a mutation.

  How do we know which value to use for the content? The `addReaction` docs tell us the `content` field has the type `ReactionContent`, which is an enum because only certain emoji reactions are supported on GitHub issues. These are the allowed values for reactions (note some values differ from their corresponding emoji names):

| Content | Emoji |
|---------|-------|
| `+1` | 👍 |
| `-1` | 👎 |
| `laugh` | 😄 |
| `confused` | 😕 |
| `heart` | ❤️ |
| `hooray` | 🎉 |
| `rocket` | 🚀 |
| `eyes` | 👀 |

* The rest of the call is composed of the payload object. This is where we specify the data we want the server to return after we've performed the mutation. These lines come from the `addReaction` docs, which three possible return fields:

  * `clientMutationId` (`String`)
  * `reaction` (`Reaction!`)
  * `subject` (`Reactable!`)

  In this example, we return the two required fields (`reaction` and `subject`), both of which have required subfields (respectively, `content` and `id`).

When we run the mutation, this is the response:

```json
{
  "data": {
    "addReaction": {
      "reaction": {
        "content": "HOORAY"
      },
      "subject": {
        "id": "MDU6SXNzdWUyMTc5NTQ0OTc="
      }
    }
  }
}
```

That's it! Check out your reaction to the issue by hovering over the :tada: to find your username.

One final note: when you pass multiple fields in an input object, the syntax can get unwieldy. Moving the fields into a variable can help. Here's how you could rewrite the original mutation using a variable:

```graphql
mutation($myVar:AddReactionInput!) {
  addReaction(input:$myVar) {
    reaction {
      content
    }
    subject {
      id
    }
  }
}
variables {
  "myVar": {
    "subjectId":"MDU6SXNzdWUyMTc5NTQ0OTc=",
    "content":"HOORAY"
  }
}
```

> [!NOTE]
> You may notice that the `content` field value in the earlier example (where it's used directly in the mutation) does not have quotes around `HOORAY`, but it does have quotes when used in the variable. There's a reason for this:
>
> * When you use `content` directly in the mutation, the schema expects the value to be of type `ReactionContent`, which is an *enum*, not a string. Schema validation will throw an error if you add quotes around the enum value, as quotes are reserved for strings.
> * When you use `content` in a variable, the variables section must be valid JSON, so the quotes are required. Schema validation correctly interprets the `ReactionContent` type when the variable is passed into the mutation during execution.
>
> For more information on the difference between enums and strings, see the official GraphQL spec.

### Further reading

There is a *lot* more you can do when forming GraphQL calls. Here are some places to look next:

* Using pagination in the GraphQL API
* Fragments
* Inline fragments
* Directives

---

## Using GraphQL Clients

> Source: https://docs.github.com/en/graphql/guides/using-graphql-clients

> **Note (mirror):** The listed URLs https://docs.github.com/en/graphql/guides/using-the-explorer and https://docs.github.com/en/graphql/overview/explorer both redirect here. The GraphQL Explorer was removed from the documentation on November 11, 2025; this "Using GraphQL Clients" page is the closest equivalent.

You can run queries on real GitHub data using various GraphQL clients and libraries.

> [!WARNING]
> The GraphQL Explorer was removed from the documentation on November 11, 2025. See our changelog announcement about this change.

### Using GraphQL client IDEs

There are many open-source GraphQL client IDEs you can use to access GitHub's GraphQL API.

See the guide on forming calls with GraphQL for extensive information on HTTP methods, authentication, and GraphQL call structure.

First, choose a client. Common options include GraphiQL, Insomnia, and Altair (desktop/web/extension). You can see the full list of clients in the GraphQL organization's tool directory.

The following generic instructions will work with most GraphQL clients:

1. Point the client at the GraphQL endpoint: `https://api.github.com/graphql`.

2. Add an `Authorization` header: `Authorization: Bearer TOKEN` (replace `TOKEN` with your GitHub personal access token. For more information, see the guide on managing your personal access tokens).

3. Set the request method to `POST` or if it's available, use the client-provided GraphQL mode.

4. Enter your query or mutation in the editor and, if needed, provide variables in the "Variables" panel.

   Example:

   ```graphql
   query {
     viewer {
       login
     }
   }
   ```

5. If your client needs a schema for documentation rendering or autocomplete, fetch it via a GraphQL introspection query. Many clients can do this automatically from the "Docs" panel.

   Minimal introspection query:

   ```graphql
   query IntrospectionQuery {
     __schema {
       types {
         name
       }
     }
   }
   ```

6. Run the request and inspect the JSON response. The example query should return the login associated with your authenticated GitHub personal access token.

Use the client UI to explore docs, run queries, and save requests as needed.

### GitHub CLI

You can also use the command line with GitHub CLI to run GraphQL queries.

1. Install and authenticate with GitHub CLI.
2. Run a query against `https://api.github.com/graphql` using the GraphQL endpoint with the `gh api` subcommand.

Example:

```shell
gh api graphql -f query='query { viewer { login } }'
```

This should return the login associated with your authenticated GitHub personal access token.

### Requesting support

For questions, bug reports, and discussions about GitHub Apps, OAuth apps, and API development, explore the API and Webhooks category in GitHub's Community Discussions. The discussions are moderated and maintained by GitHub staff, and answered by the GitHub community.

Consider reaching out to GitHub Support directly using the contact form for:

* Guaranteed response from GitHub staff
* Support requests involving sensitive data or private concerns
* Feature requests
* Feedback about GitHub products

---

## Rate limits and query limits for the GraphQL API

> Source: https://docs.github.com/en/graphql/overview/rate-limits-and-query-limits-for-the-graphql-api

> **Note (mirror):** The listed URL https://docs.github.com/en/graphql/overview/resource-limitations redirects here. "Rate limits and query limits for the GraphQL API" is the current title for what was formerly "Resource limitations."

The GitHub GraphQL API has limitations in place to protect against excessive or abusive calls to GitHub's servers.

### Primary rate limit

The GraphQL API assigns points to each query and limits the points that you can use within a specific amount of time. This limit helps prevent abuse and denial-of-service attacks, and ensures that the API remains available for all users.

The REST API also has a separate primary rate limit. For more information, see [Rate limits for the REST API](/en/rest/overview/rate-limits-for-the-rest-api).

In general, you can calculate your primary rate limit for the GraphQL API based on your method of authentication:

* *For users*: 5,000 points per hour per user. This includes requests made with a personal access token as well as requests made by a GitHub App or OAuth app on behalf of a user that authorized the app. Requests made on a user's behalf by a GitHub App that is owned by a GitHub Enterprise Cloud organization have a higher rate limit of 10,000 points per hour. Similarly, requests made on your behalf by an OAuth app that is owned or approved by a GitHub Enterprise Cloud organization have a higher rate limit of 10,000 points per hour if you are a member of the GitHub Enterprise Cloud organization.
* *For GitHub App installations not on a GitHub Enterprise Cloud organization*: 5,000 points per hour per installation. Installations that have more than 20 repositories receive another 50 points per hour for each repository. Installations that are on an organization that have more than 20 users receive another 50 points per hour for each user. The rate limit cannot increase beyond 12,500 points per hour. The rate limit for user access tokens (as opposed to installation access tokens) are dictated by the primary rate limit for users.
* *For GitHub App installations on a GitHub Enterprise Cloud organization*: 10,000 points per hour per installation. The rate limit for user access tokens (as opposed to installation access tokens) are dictated by the primary rate limit for users.
* *For OAuth apps*: 5,000 points per hour, or 10,000 points per hour if the app is owned by a GitHub Enterprise Cloud organization. This only applies when the app uses their client ID and client secret to request public data. The rate limit for OAuth access tokens generated by a OAuth app are dictated by the primary rate limit for users.
* *For `GITHUB_TOKEN` in GitHub Actions workflows*: 1,000 points per hour per repository. For requests to resources that belong to an enterprise account on GitHub.com, the limit is 15,000 points per hour per repository.

You can check the point value of a query or calculate the expected point value as described in the following sections. The formula for calculating points and the rate limit are subject to change.

#### Checking the status of your primary rate limit

You can use the headers that are sent with each response to determine the current status of your primary rate limit.

| Header name             | Description                                                                                                    |
| ----------------------- | -------------------------------------------------------------------------------------------------------------- |
| `x-ratelimit-limit`     | The maximum number of points that you can use per hour                                                         |
| `x-ratelimit-remaining` | The number of points remaining in the current rate limit window                                                |
| `x-ratelimit-used`      | The number of points you have used in the current rate limit window                                            |
| `x-ratelimit-reset`     | The time at which the current rate limit window resets, in UTC epoch seconds                                   |
| `x-ratelimit-resource`  | The rate limit resource that the request counted against. For GraphQL requests, this will always be `graphql`. |

You can also query the `rateLimit` object to check your rate limit. When possible, you should use the rate limit response headers instead of querying the API to check your rate limit.

```graphql
query {
  viewer {
    login
  }
  rateLimit {
    limit
    remaining
    used
    resetAt
  }
}
```

| Field       | Description                                                                  |
| ----------- | ---------------------------------------------------------------------------- |
| `limit`     | The maximum number of points that you can use per hour                       |
| `remaining` | The number of points remaining in the current rate limit window              |
| `used`      | The number of points you have used in the current rate limit window          |
| `resetAt`   | The time at which the current rate limit window resets, in UTC epoch seconds |

#### Returning the point value of a query

You can return the point value of a query by querying the `cost` field on the `rateLimit` object:

```graphql
query {
  viewer {
    login
  }
  rateLimit {
    cost
  }
}
```

#### Predicting the point value of a query

You can also roughly calculate the point value of a query before you make the query.

1. Add up the number of requests needed to fulfill each unique connection in the call. Assume every request will reach the `first` or `last` argument limits.
2. Divide the number by **100** and round the result to the nearest whole number to get the final aggregate point value. This step normalizes large numbers.

> [!NOTE]
> The minimum point value of a call to the GraphQL API is **1**.

Here's an example query and score calculation:

```graphql
query {
  viewer {
    login
    repositories(first: 100) {
      edges {
        node {
          id

          issues(first: 50) {
            edges {
              node {
                id

                labels(first: 60) {
                  edges {
                    node {
                      id
                      name
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

This query requires 5,101 requests to fulfill:

* Although we're returning 100 repositories, the API has to connect to the viewer's account **once** to get the list of repositories. So, requests for repositories = **1**
* Although we're returning 50 issues, the API has to connect to each of the **100** repositories to get the list of issues. So, requests for issues = **100**
* Although we're returning 60 labels, the API has to connect to each of the **5,000** potential total issues to get the list of labels. So, requests for labels = **5,000**
* Total = **5,101**

Dividing by 100 and rounding gives us the final score of the query: **51**

### Secondary rate limits

In addition to primary rate limits, GitHub enforces secondary rate limits in order to prevent abuse and keep the API available for all users.

You may encounter a secondary rate limit if you:

* *Make too many concurrent requests.* No more than 100 concurrent requests are allowed. This limit is shared across the REST API and GraphQL API.
* *Make too many requests to a single endpoint per minute.* No more than 900 points per minute are allowed for REST API endpoints, and no more than 2,000 points per minute are allowed for the GraphQL API endpoint. For more information about points, see [Calculating points for the secondary rate limit](#calculating-points-for-the-secondary-rate-limit).
* *Make too many requests per minute.* No more than 90 seconds of CPU time per 60 seconds of real time is allowed. No more than 60 seconds of this CPU time may be for the GraphQL API. You can roughly estimate the CPU time by measuring the total response time for your API requests.
* *Make too many requests that consume excessive compute resources in a short period of time.*
* *Create too much content on GitHub in a short amount of time.* In general, no more than 80 content-generating requests per minute and no more than 500 content-generating requests per hour are allowed. Some endpoints have lower content creation limits. Content creation limits include actions taken on the GitHub web interface as well as via the REST API and GraphQL API.
* *Make too many OAuth access token requests in a short period of time.* No more than 2,000 OAuth access token requests per hour are allowed for GitHub Apps and OAuth apps.

These secondary rate limits are subject to change without notice. You may also encounter a secondary rate limit for undisclosed reasons.

#### Calculating points for the secondary rate limit

Some secondary rate limits are determined by the point values of requests. For GraphQL requests, these point values are separate from the point value calculations for the primary rate limit.

| Request                                                    | Points |
| ---------------------------------------------------------- | ------ |
| GraphQL requests without mutations                         | 1      |
| GraphQL requests with mutations                            | 5      |
| Most REST API `GET`, `HEAD`, and `OPTIONS` requests        | 1      |
| Most REST API `POST`, `PATCH`, `PUT`, or `DELETE` requests | 5      |

Some REST API endpoints have a different point cost that is not shared publicly.

### Exceeding the rate limit

If you exceed your primary rate limit, the response status will still be `200`, but you will receive an error message, and the value of the `x-ratelimit-remaining` header will be `0`. You should not retry your request until after the time specified by the `x-ratelimit-reset` header.

If you exceed a secondary rate limit, the response status will be `200` or `403`, and you will receive an error message that indicates that you hit a secondary rate limit. If the `retry-after` response header is present, you should not retry your request until after that many seconds has elapsed. If the `x-ratelimit-remaining` header is `0`, you should not retry your request until after the time, in UTC epoch seconds, specified by the `x-ratelimit-reset` header. Otherwise, wait for at least one minute before retrying. If your request continues to fail due to a secondary rate limit, wait for an exponentially increasing amount of time between retries, and throw an error after a specific number of retries.

Continuing to make requests while you are rate limited may result in the banning of your integration.

### Staying under the rate limit

To avoid exceeding a rate limit, you should pause at least 1 second between mutative requests and avoid concurrent requests.

You should also subscribe to webhook events instead of polling the API for data. For more information, see [Webhooks documentation](/en/webhooks).

You can also stream the audit log in order to view API requests. This can help you troubleshoot integrations that are exceeding the rate limit. For more information, see [Streaming the audit log for your enterprise](/en/enterprise-cloud@latest/admin/monitoring-activity-in-your-enterprise/reviewing-audit-logs-for-your-enterprise/streaming-the-audit-log-for-your-enterprise).

### Node limit

To pass [schema](/en/graphql/guides/introduction-to-graphql#schema) validation, all GraphQL API [calls](/en/graphql/guides/forming-calls-with-graphql) must meet these standards:

* Clients must supply a `first` or `last` argument on any [connection](/en/graphql/guides/introduction-to-graphql#connection).
* Values of `first` and `last` must be within 1-100.
* Individual calls cannot request more than 500,000 total [nodes](/en/graphql/guides/introduction-to-graphql#node).

#### Calculating nodes in a call

These two examples show how to calculate the total nodes in a call.

1. Simple query (the highlighted `first` argument values are `50` for `repositories` and `10` for `issues`):

   ```graphql
   query {
     viewer {
       repositories(first: 50) {
         edges {
           repository:node {
             name

             issues(first: 10) {
               totalCount
               edges {
                 node {
                   title
                   bodyHTML
                 }
               }
             }
           }
         }
       }
     }
   }
   ```

   Calculation:

   ```
   50         = 50 repositories
    +
   50 x 10  = 500 repository issues

               = 550 total nodes
   ```

2. Complex query (the highlighted `first` argument values are `50` for `repositories`, `20` for `pullRequests`/`issues`, and `10` for `comments`/`followers`):

   ```graphql
   query {
     viewer {
       repositories(first: 50) {
         edges {
           repository:node {
             name

             pullRequests(first: 20) {
               edges {
                 pullRequest:node {
                   title

                   comments(first: 10) {
                     edges {
                       comment:node {
                         bodyHTML
                       }
                     }
                   }
                 }
               }
             }

             issues(first: 20) {
               totalCount
               edges {
                 issue:node {
                   title
                   bodyHTML

                   comments(first: 10) {
                     edges {
                       comment:node {
                         bodyHTML
                       }
                     }
                   }
                 }
               }
             }
           }
         }
       }

       followers(first: 10) {
         edges {
           follower:node {
             login
           }
         }
       }
     }
   }
   ```

   Calculation:

   ```
   50              = 50 repositories
    +
   50 x 20       = 1,000 pullRequests
    +
   50 x 20 x 10 = 10,000 pullRequest comments
    +
   50 x 20       = 1,000 issues
    +
   50 x 20 x 10 = 10,000 issue comments
    +
   10              = 10 followers

                    = 22,060 total nodes
   ```

### Timeouts

If GitHub takes more than 10 seconds to process an API request, GitHub will terminate the request and you will receive a timeout response and a message reporting that "We couldn't respond to your request in time".

GitHub reserves the right to change the timeout window to protect the speed and reliability of the API.

You can check the status of the GraphQL API at [githubstatus.com](https://www.githubstatus.com/) to determine whether the timeout is due to a problem with the API. You can also try to simplify your request or try your request later. For example, if you are requesting a large number of objects in a single request, you can try requesting fewer objects split over multiple queries.

If a timeout occurs for any of your API requests, additional points will be deducted from your primary rate limit for the next hour to protect the speed and reliability of the API.

### Other resource limits

To protect the speed and reliability of the API, GitHub also enforces other resource limitations. If your GraphQL query consumes too many resources, GitHub will terminate the request and return partial results along with an error indicating that resource limits were exceeded.

**Examples of queries that may exceed resource limits:**

* Requesting thousands of objects or deeply nested relationships in a single query.
* Using large `first` or `last` arguments in multiple connections simultaneously.
* Fetching extensive details for each object, such as all comments, reactions, and related issues for every repository.

### Query optimization strategies

* **Limit the number of objects**: Use smaller values for `first` or `last` arguments and paginate through results.
* **Reduce query depth**: Avoid requesting deeply nested objects unless necessary.
* **Filter results**: Use arguments to filter data and return only what you need.
* **Split large queries**: Break up complex queries into multiple simpler queries.
* **Request only required fields**: Select only the fields you need, rather than requesting all available fields.

By following these strategies, you can reduce the likelihood of hitting resource limits and improve the performance and reliability of your API requests.

---

## Using pagination in the GraphQL API

> Source: https://docs.github.com/en/graphql/guides/using-pagination-in-the-graphql-api

Learn how to traverse data sets using cursor based pagination with the GraphQL API.

### About pagination

GitHub's GraphQL API limits the number of items that you can fetch in a single request in order to protect against excessive or abusive requests to GitHub's servers. When you use the GraphQL API, you must supply a `first` or `last` argument on any connection. The value of these arguments must be between 1 and 100. The GraphQL API will return the number of connections specified by the `first` or `last` argument.

If the data that you are accessing has more connections than the number of items specified by the `first` or `last` argument, the response is divided into smaller "pages" of the specified size. These pages can be fetched one at a time until the entire data set has been retrieved. Each page contains the number of items specified by the `first` or `last` argument, unless it is the last page, which may contain a lower number of items.

This guide demonstrates how to request additional pages of results for paginated responses, how to change the number of results returned on each page, and how to write a script to fetch multiple pages of results.

### Requesting a `cursor` in your query

When using the GraphQL API, you use cursors to traverse through a paginated data set. The cursor represents a specific position in the data set. You can get the first and last cursor on a page by querying the `pageInfo` object. For example:

```graphql
query($owner: String!, $name: String!) {
  repository(owner: $owner, name: $name) {
    pullRequests(first: 100, after: null) {
      nodes {
        createdAt
        number
        title
      }
      pageInfo {
        endCursor
        startCursor
        hasNextPage
        hasPreviousPage
      }
    }
  }
}
```

In this example, `pageInfo.startCursor` gives the cursor for the first item on the page. `pageInfo.endCursor` gives the cursor for the last item on the page. `pageInfo.hasNextPage` and `pageInfo.hasPreviousPage` indicate whether there is a page before and after the page that was returned.

### Changing the number of items per page

The `first` and `last` arguments control how many items are returned. The maximum number of items you can fetch using the `first` or `last` argument is 100. You may need to request fewer than 100 items if your query touches a lot of data in order to avoid hitting a rate or node limit. For more information, see [Rate limits and query limits for the GraphQL API](/en/graphql/overview/rate-limits-and-query-limits-for-the-graphql-api).

### Traversing the data set using pagination

Once you return a cursor from a query, you can use the cursor to request the next page of results. To do so, you will use the `after` or `before` argument and the cursor.

For example, assuming the `pageInfo.endCursor` value from the previous example was `Y3Vyc29yOnYyOpHOUH8B7g==`, you can use this query to request the next page of results:

```graphql
query($owner: String!, $name: String!) {
  repository(owner: $owner, name: $name) {
    pullRequests(first: 1, after: "Y3Vyc29yOnYyOpHOUH8B7g==") {
      nodes {
        createdAt
        number
        title
      }
      pageInfo {
        endCursor
        hasNextPage
        hasPreviousPage
      }
    }
  }
}
```

You can continue to send queries with the new `pageInfo.endCursor` value returned in the response until there are no pages left to traverse, indicated by `pageInfo.hasNextPage` returning `false`.

If you specified the `last` instead of the `first` argument, the last page of results will be returned first. In this case, you will use the `pageInfo.startCursor` value and the `before` argument to get the previous page of results. Once `pageInfo.hasPreviousPage` returns `false`, you have reached the last page. For example:

```graphql
query($owner: String!, $name: String!) {
  repository(owner: $owner, name: $name) {
    pullRequests(last: 1, before: "R3Vyc29yOnYyOpHOHcfoOg==") {
      nodes {
        createdAt
        number
        title
      }
      pageInfo {
        startCursor
        hasPreviousPage
      }
    }
  }
}
```

### Next steps

You can use GitHub's Octokit SDK and the `octokit/plugin-paginate-graphql` plugin to support pagination in your scripts. For more information, see [plugin-paginate-graphql.js](https://github.com/octokit/plugin-paginate-graphql.js).

---

## Public schema

> Source: https://docs.github.com/en/graphql/overview/public-schema

Download the public schema for the GitHub GraphQL API.

You can [perform introspection](/en/graphql/guides/introduction-to-graphql#discovering-the-graphql-api) against the GraphQL API directly.

Alternatively, you can download the latest version of the public schema here:

[`schema.docs.graphql`](/public/fpt/schema.docs.graphql)
