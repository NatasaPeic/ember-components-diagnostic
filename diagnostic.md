# Ember Components Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  Give an example of a visual hierarchy that could be modeled with components.

    ```md
    Sign up form

    Components:
    1. sign-up-form (this component holds next 3 components)
    2. email-input
    3. password-input
    4. password-confirmation-input

    We create these components, so we can reuse them on different view states like sign in.
    ```

1.  What is the command to generate a new component called '`my-map`'?

    ```sh
    ember g component my-map
    ```

1.  What files are edited to produce a component, and what are their
    responsibilities?

    ```md
    1. template.js
    - it can hold other components (optional)
    - it holds the actions that are sent up to the route of where that component was invoked


    2. component.js
    - holds actions that are going to be send when event occur (click or submit)
    - holds classes that we use for styling
    ```

1.  Suppose you have a component '`my-contact`', which is loaded from
    '`app/contacts/template.hbs`' when visiting the `/contacts` path. What is
    the syntax for loading this component inside that template?

    ```html
    my-contact has component.js file and template.hbs file
    contacts route has route.js file and template.hbs file

    Loading my-contact inside contact template

    my-contact component template holds action that are triggered on event, and sent up to the route contact.

    To load this component we call that component using {{}} in contact route.js

    {{my-contact contact=model }}


    ```

    Each contact has multiple phone numbers. Suppose you also have '`my-phone`'
    nested under '`my-contact`'. What is the code you would write in
    '`app/components/my-contact/template.hbs`' to load the nested component and
    pass it data?

    ```html
    my-phone is nested under my-contact

    my-contact component template

    {{#each model as |phone|}
    {{my-contact/my-phone phone=phone}}
    {{/each}}
    ```
