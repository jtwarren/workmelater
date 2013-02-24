Python classes:

  BaseTask() - class which abstracts a lot of cruft around a normal task
    - def encode_json():
    	return a task as a JSON
    - def decode_json():
    	return python datastructure from JSON
    - def enqueue():
    	Enqueue task into a given redis server. rpush to redis list
    - def process():
    	This should be implemented by the extended class. But we can log time
    	taken etc in this method
    - def set_priority():
    	sets an attribute called priority which decides the queue

  Worker() - class which lpops job from a given redis list and calls
     		 process() method on the job
    - def reserve():
    	reserve a task from redis and call process() on the task

A couple of simple bash scripts to start Worker in a infinite loop.