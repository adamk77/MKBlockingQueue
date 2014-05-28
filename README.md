MKBlockingQueue
===============

Simple bocking queue implementation in Objective-C.

Example:

    - (void)producerThread
    {
        while (YES)
        {
            [_blockingQueue enqueue:[NSString stringWithFormat:@"Test string %d", arc4random()%30000]];
            [NSThread sleepForTimeInterval:arc4random()%3+1];
        }
    }

    - (void)consumerThread
    {
        while (YES)
        {
            // This will block until there is data
            NSString *s = [_blockingQueue dequeue];
            NSLog(@"Dequeued: %@", s];
        }
    }

See the project ProducerConsumerTest for a working iOS sample.
