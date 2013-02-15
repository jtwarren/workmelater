##WorkMeLater
WorkMeLater is an asynchronous queuing system built in python to process tasks later. It was inspired by github's [resque](https://github.com/defunkt/resque) system built to handle asynchronous tasks.

##Project goals
We are a heavy user of [pyres](https://github.com/binarydud/pyres) which is a resque clone built in python.  There are several requirements we had that pyres did not support.  Eventually we decided to build a new project to suit our needs.

    - Support the ability to monkey path socket using gevent / eventlet for concurrency
    - Support priority based queuing out of the box
    - Use Flask for the webadmin
    - Built in support for sharding tasks among redis instances
    - Use LPOP instead of BLPOP so that worker are not starved on higher priority
        tasks, they can work on low priority ones as well
    - ability to restart worker after X number of tasks
