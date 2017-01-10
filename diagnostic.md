# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Router: maps URLs to routes and passes any relevant parameters to the route
      handler for that route. This is where you define routes.
    Route: parse the URL for a given route and use information from that URL to load model data.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Boston{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first route definition has a nested route, so the parent url will be at the URL
    `/products` while the child (for the first product) will be at `products/1`
    or something similar.

    The second is a single route that will have the url `products/1` for the first
    produc.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    Pass params to the model hook and use params.movie_id to access the id.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    We can access it by referencing the model with {{model}}. You can also use the
    each Handlebars helper like so:
    {{#each model as |thing|}}
      <li>{{thing.example}}</li>
    {{/each}}

    ```
