## Core Actions

1. View Notifications
2. Mark Notification as Read
3. Mark All Notifications as Read
4. Get Unread Notification Count
5. Receive Real-Time Notifications

## API 1: Get All Notifications

Method: GET

Endpoint:
/api/notifications

Headers:
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJNYXBDbGFpbXMiOnsiYXVkIjoiaHR0cDovLzIwLjI0NC41Ni4xNDQvZXZhbHVhdGlvbi1zZXJ2aWNlIiwiZW1haWwiOiJkaXZ5YWJoYWRvdXJpeWExMjM0QGdtYWlsLmNvbSIsImV4cCI6MTc4MTE2NDcwMCwiaWF0IjoxNzgxMTYzODAwLCJpc3MiOiJBZmZvcmQgTWVkaWNhbCBUZWNobm9sb2dpZXMgUHJpdmF0ZSBMaW1pdGVkIiwianRpIjoiZGIyM2UwMmMtZDBjMi00OGYzLTlkYTgtZjJmZWZjMmVmNjMxIiwibG9jYWxlIjoiZW4tSU4iLCJuYW1lIjoiZGl2eWEgc2luZ2giLCJzdWIiOiI5MzM3NjI2MS1hZmFhLTQ3YTUtYjQ2Ni1hNWRhNjIyOTNkM2IifSwiZW1haWwiOiJkaXZ5YWJoYWRvdXJpeWExMjM0QGdtYWlsLmNvbSIsIm5hbWUiOiJkaXZ5YSBzaW5naCIsInJvbGxObyI6IjIzMDA0NjAxMjAwMjMiLCJhY2Nlc3NDb2RlIjoiQkFWRFNoIiwiY2xpZW50SUQiOiI5MzM3NjI2MS1hZmFhLTQ3YTUtYjQ2Ni1hNWRhNjIyOTNkM2IiLCJjbGllbnRTZWNyZXQiOiJVUkRZanhBcHR5V05RaEFDIn0.0lVH3LceyfTmEGJOi8AFRvsldcv3tCwwrhov53wvXYU

{
  "notifications": [
    {
      "id": 1,
      "title": "Placement Drive",
      "message": "Amazon hiring now",
      "isRead": false,
      "createdAt": "2026-06-11T10:00:00Z"
    }
  ]
}

## API 2: Mark Notification as Read

Method: PATCH

Endpoint:
/api/notifications/91c468ef-a4c4-4466-afcb-3dfb011d3b9a/read

{
  "message": "Notification marked as read"
}

## API 3: Mark All Notifications as Read

Method: PATCH

Endpoint:
/api/notifications/read-all

{
  "message": "All notifications marked as read"
}

## API 4: Get Unread Count

Method: GET

Endpoint:
/api/notifications/unread-count

{
  "count": 5
}

## Notification JSON Schema

{
  "id": 1,
  "userId": 101,
  "title": "Placement Update",
  "message": "Interview Scheduled",
  "isRead": false,
  "createdAt": "2026-06-11T10:00:00Z"
}

## Real-Time Notification Mechanism

WebSocket will be used for real-time notifications.

Flow:
1. User logs in.
2. WebSocket connection is established.
3. Backend pushes new notifications instantly.
4. User receives notifications without refreshing the page.

