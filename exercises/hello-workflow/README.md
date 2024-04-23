# Exercise 1: Hello Workflow

During this exercise, you will

- Review the business logic of the provided Workflow Definition to understand its behavior
- Modify the Worker initialization code to specify a task queue name
- Run the Worker initialization code to start the Worker process
- Execute the Workflow from the command line, specifying your name as input

Make your changes to the code in the `practice` subdirectory (look for TODO
comments that will guide you to where you should make changes to the code).
If you need a hint or want to verify your changes, look at the complete version
in the `solution` subdirectory.

## GitPod Environment Shortcuts

If you are executing the exercises in the provided GitPod environment, you
can take advantage of certain aliases to aid in navigation and execution of
the code.

| Command | Action                                                                                                                         |
| :------ | :----------------------------------------------------------------------------------------------------------------------------- |
| `ex1`   | Change to Exercise 1 Practice Directory                                                                                        |
| `ex1s`  | Change to Exercise 1 Solution Directory                                                                                        |
| `ex1w`  | Execute the Exercise 1 Worker. Must be within the appropriate directory for this to succeed. (either `practice` or `solution`) |

## Part A: Review the Workflow Business Logic

1. Open the `HelloWorkflowWorkflow.java` and `HelloWorkflowWorkflowImpl.java` files (located in the `practice/src/main/java/helloworkflow` subdirectory) in the editor
2. Review the input parameters, business logic, and return value.

## Part B: Specify a Task Queue Name for the Worker

1. Open the `HelloWorkflowWorker.java` file (located in the `practice/src/main/java/helloworkflow` subdirectory) in the editor
2. Specify `greeting-tasks` as the name of the task queue
3. Save your changes

## Part C1: Fetch the Dependencies and Compile the Code

1. Open a terminal window in the environment and change to the `practice` subdirectory for this exercise
2. Run the following command to compile the code, as well as download and install the Java dependencies needed by the code, which will include the Temporal Java SDK

```
$ mvn compile
```

## Part C2: Start the Worker

2. Run the following command in the terminal window to start the Worker

```
$ mvn compile exec:java -Dexec.mainClass="helloworkflow.HelloWorkflowWorker"
```

## Part D: Start the Workflow from the Command Line

1. Open another terminal window in the environment and change to the `practice` subdirectory for this exercise
2. Run the following command, replacing `Mason` with your first name. Be sure to retain the same quoting shown here when you run the command:

```
$ temporal workflow start \
    --type HelloWorkflowWorkflow \
    --task-queue greeting-tasks \
    --workflow-id my-first-workflow \
    --input '"Mason"'
```

Note that this command starts the Workflow, but it does not wait for it to complete or show the result.
If you have time, continue with the optional part of the exercise below to see how to view the result using `temporal`.

## Part E (Optional): Display the Result

You can run the following command to display the result of a Workflow Execution:

```
temporal workflow show --workflow-id my-first-workflow
```

It is also possible, and often more convenient, to view this information using the Web UI. You will
have a chance to do this in the next exercise.

### This is the end of the exercise.
