# Asterisk-queue-with-change-position-implementation
A new working implementation for asterisk queue to process with change queue position. 

Implementation includes CLI command "queue position caller" and manager action "QueueChangePositionCaller".

To use it, download the newest LTS version of Asterisk (now is 16-16/09/2020). Unzip it in working directory. Enter into asterisk-{version}/apps and paste app_queue.c into it. Build (make make install) and reload asterisk. 

That's it! Your own queue with changing position is now yours!

Now try in asterisk CLI "queue position caller". If you see:


        Change position of a channel on a queue.
        It is highly not recommended to use this when queue is bigger
        than 10.
        You cannot change position to higher than queue size or if
        queue is not full then last position of active caller
        first position is always reserved.
        
        
Then changing caller queue position is working!

You can see also when enter "manager show command QueueChangePriorityCaller" manager action syntax:

        [Syntax]
        Action: QueueChangePriorityCaller
        [ActionID:] <value>
        Queue: <value>
        Caller: <value>
        Priority: <value>

        [Synopsis]
        Change priority of a caller on queue. 

        [Description]
        Not available

        [Arguments]
        ActionID
            ActionID for this transaction. Will be returned.
        Queue
            The name of the queue to take action on.
        Caller
            The caller (channel) to change priority on queue.
        Priority
            Priority value for change for caller on queue.

        [See Also]
        Not available

        [Privilege]
        <none>

        [List Responses]
        None

        [Final Response]
        None
        
This file is distributed under Apache license 2.0.
