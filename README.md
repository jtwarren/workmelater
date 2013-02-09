workmelater is a asynchronous queuing system built in python to process tasks
later. It is designed after github's resque system.

Project goals:
 We are a heavy user of [pyres](https://github.com/binarydud/pyres) which is a
resque clone built in python. But we had several requirements which required us
to hack pyres to support it. Eventually we decided to build a new project to suit
our requirements.

  - Support ability to monkey path socket using gevent/eventlet for concurrency
  - Support priority based queuing out of the box
  - Use Flask for the webadmin
  - Built in support for sharding tasks among redises
  - Use LPOP instead of BLPOP so that worker are not starved on higher priority
    tasks, they can work on low priority ones as well
  - ability to restart worker after X number of tasks

