# thread_messages

Get messages from a thread.

## Request

```json
{
    "cmd": "thread_messages",
    "thread_id": "uuid-here",
    "start": null,
    "limit": 100
}
```

### Parameters

| Parameter   | Type          | Required | Description                                       |
|-------------|---------------|----------|---------------------------------------------------|
| `thread_id` | string        | Yes      | The thread ID                                     |
| `start`     | string/int    | No       | Message ID to start before, or number to skip     |
| `limit`     | int           | No       | Maximum messages to return (default: 100, max: 200) |

## Response

### Success

```json
{
    "cmd": "thread_messages",
    "thread_id": "uuid-here",
    "messages": [
        {
            "user": "alice",
            "content": "Hello everyone!",
            "timestamp": 1234567890.123,
            "type": "message",
            "pinned": false,
            "id": "msg-uuid"
        }
    ]
}
```

### Error Responses

| Error Message                     | Cause                        |
|-----------------------------------|------------------------------|
| `"Thread ID is required"`         | Missing thread_id parameter  |
| `"Thread not found"`              | Thread doesn't exist         |
| `"User roles not found"`          | User has no roles            |
| `"You do not have permission..."` | Missing view permission      |

## Permissions

Requires `view` permission in the parent channel.

## Related

- [thread_get](thread_get.md) - Get thread details
- [message_new](message_new.md) - Send a message to a thread
