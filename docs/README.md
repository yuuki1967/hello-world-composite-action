# How to deploy the composite action into a workflow.
## In another repository, you should call yuuki1967/hello-world-composite-action@v3 with input value 
```
on: workflow_dispatch

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v3
      - id: foo
        uses: yuuki1967/hello-world-composite-action@v3
        with:
          MY_NAME: 'yuuki'
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
 ```
