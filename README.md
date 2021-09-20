# StepZen REST Example

An example showing how to make a REST API available as GraphQL API through StepZen.

## Getting started

Before you're able to try out this example, you need to make sure that StepZen is installed on your local machine and that you're logged in. You can find how to do this in the [Getting Started with StepZen](https://stepzen.com/docs/quick-start) guide.

After cloning this repository you need to run the following command to start this example:

```
stepzen start
```

This will make a GraphQL API available at [http://localhost:5000/api/rest-example](http://localhost:5000/api/rest-example) with the GraphiQL Playground.

## Sending requests

This project is using [My JSON Server](https://my-json-server.typicode.com/) to create a free REST API based on the contents of `db.json` in this repository. You can view an example of this REST API [here](https://my-json-server.typicode.com/stepzen-samples/stepzen-rest-example), and as you can see it has the following endpoints:

- [/products](https://my-json-server.typicode.com/stepzen-samples/stepzen-rest-example/products)
- [/products/[id]/categories](https://my-json-server.typicode.com/stepzen-samples/stepzen-rest-example/products/1/categories)
- [/products/[id]/rating](https://my-json-server.typicode.com/stepzen-samples/stepzen-rest-example/products/1/rating)

Based on the configuration that is passed to StepZen in `index.graphql` and `schema/ecommerce/graphql`, the schema for the GraphQL API is constructed. You can query the GraphQL API in example with the following query:

```graphql
query GetProduct {
  getProduct(id: 1) {
    name
    price
    category {
      name
    }
    rating {
      average
    }
  }
}
```

This query will return product information from the REST API, by calling the endpoints `/products/1`, `/products/1/categories` and `/products/1/rating` and returning all this data in one JSON blob.

## Questions

Do you have any questions on this integration, or you want to check out other integrations you can make with [StepZen](https://stepzen.com/? Have a look at the website or join the [Discord channel](https://discord.com/channels/768229795544170506) for support.

