Problem: JSON Message Processor System

Design and implement a system that processes incoming JSON messages of different types. Each message has a UUID and a type, and the system needs to handle each type differently.

Requirements:

1. The system should be able to receive JSON messages, each containing at least a UUID and a type field.
2. There are three types of messages: A, B, and C.
3. For Type A messages:
   - They should be sent to an API endpoint immediately upon receipt.
4. For Type B messages:
   - They should be batched.
   - If adding a message to the batch makes the batch size equal to 5, send the entire batch to an endpoint.
   - Only add a message to the batch if a message with the same UUID isn't already in the batch.
5. For Type C messages:
   - Save the UUID to an efficient storage type.

Initial Pseudocode:

```
Class MessageProcessor:
    Method Initialize():
        Initialize empty message queue
        Initialize batch for Type B messages
        Initialize storage for Type C UUIDs

    Method ReceiveMessage(jsonMessage):
        Add jsonMessage to message queue

    Method ProcessMessages():
        While message queue is not empty:
            message = Remove first message from queue
            ProcessMessage(message)

    Method ProcessMessage(message):
        messageType = ExtractMessageType(message)
        If messageType is "A":
            ProcessTypeA(message)
        Else If messageType is "B":
            ProcessTypeB(message)
        Else If messageType is "C":
            ProcessTypeC(message)
        Else:
            HandleUnknownMessageType(message)

    Method ProcessTypeA(message):
        SendToAPIEndpoint(message)

    Method ProcessTypeB(message):
        If message.UUID not in batch:
            Add message to batch
            If batch size == 5:
                SendBatchToEndpoint(batch)
                Clear batch

    Method ProcessTypeC(message):
        StoreUUID(message.UUID)

    Method SendToAPIEndpoint(message):
        // Send individual message to API endpoint

    Method SendBatchToEndpoint(batch):
        // Send batch of messages to API endpoint

    Method StoreUUID(UUID):
        // Store UUID in efficient storage type

// Usage
processor = new MessageProcessor()
processor.Initialize()
Start ProcessMessages() in separate thread
```

Tasks:

1. System Implementation:
   Implement the MessageProcessor system, ensuring it meets all the given requirements. You can use your preferred programming language. Pay special attention to:
   - Efficient message queuing and processing
   - Correct handling of Type B message batching
   - Efficient storage for Type C message UUIDs

3. System Enhancement:
   Modify and expand the MessageProcessor system to include the following features:
   a) Implement concurrent processing of messages to improve throughput.
   b) Add error handling and logging throughout the system.
   c) Implement a mechanism to handle system crashes and ensure no messages are lost.
   d) Create a method to query the current state of the system (e.g., number of processed messages of each type, current batch size for Type B).
   e) Design a way to easily add new message types in the future without major code changes.

4. Performance Optimization:
   Suggest and implement optimizations to ensure the system can handle a high volume of incoming messages efficiently. Consider aspects like data structures, algorithms, and potential bottlenecks.

5. Testing Strategy:
   Outline a comprehensive testing strategy for this system, including unit tests, integration tests, and performance tests. Include specific test cases that cover edge cases and potential failure scenarios.