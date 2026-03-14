# thread_delete

Delete a thread. Only the thread creator, admins, and owners can delete threads.

## Request

```json
{
    "cmd": "thread_delete",
    "thread_id": "uuid-here"
}
```

### Parameters

| Parameter   | Type   | Required | Description          |
|-------------|--------|----------|----------------------|
| `thread_id` | string | Yes      | The thread ID to delete |

## Response

### Success

```json
{
    "cmd": "thread_delete",
    "thread_id": "uuid-here",
    "channel": "announcements",
    "global": true
}
```

### Error Responses

| Error Message                     | Cause                        |
|-----------------------------------|------------------------------|
| `"Thread ID is required"`         | Missing thread_id parameter  |
| `"Thread not found"`              | Thread doesn't exist         |
| `"User roles not found"`          | User has no roles            |
| `"You do not have permission..."` | Not creator/admin/owner      |

## Permissions

- Thread creator can delete their own threads
- Admins and owners can delete any thread

## Related

- [thread_create](thread_create.md) - Create a new thread
- [thread_update](thread_update.md) - Update thread properties
