# template-example
Screwdriver example for validating, publishing, and tagging(promoting) multiple templates

In this example, we use the [screwdriver-template-main npm package](https://github.com/screwdriver-cd/template-main) to assist with template validation, publishing, and tagging.

This example will publish two templates:
1. `golang/init`
2. `nodejs/test`

It will also tag the latest versions with the `latest` and/or `stable` tags, respectively. The `golang/init` template is located at the default template path `sd-template.yaml`, while the `nodejs/test` template is in a custom path `templates/nodejs.yaml`.

For the `nodejs/test` template, we run [a remote test](https://github.com/screwdriver-cd-test/template-test-example) that has a simple nodejs app which will directly consume the `nodejs/test` template. If that test is successful, the `promote_nodejs_template` will run using [remote triggers](https://docs.screwdriver.cd/user-guide/configuration/workflow#remote-triggers) and tag the latest `nodejs/test` template with the `stable` tag.

See the [templates documentation](https://docs.screwdriver.cd/user-guide/templates) for more information.
