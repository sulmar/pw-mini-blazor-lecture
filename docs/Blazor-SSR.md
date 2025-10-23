# Blazor SSR (Blazor Server Side Rendering)

## Sequence Diagram

```mermaid
sequenceDiagram

participant C as Client (Browser)
participant S as Blazor Server
participant H as SignalR Connection

  

C->>S: 1. Initial page request (HTML shell + Blazor script)
S-->>C: 2. Return HTML + Blazor Server script
C->>H: 3. Establish SignalR connection (WebSocket)
C->>C: 4. Render UI in browser (based on server state)

  

Note over C,S: Later – user interacts with UI (e.g., clicks button)

  

C->>S: 5. Send event to server via SignalR
S->>S: 6. Execute event handler (.NET on server)
S-->>C: 7. Send updated UI diff via SignalR
C->>C: 8. Apply diff to DOM (no page reload)
```


## 🧩 Blazor Server — SSR + SignalR


- `UserList.razor`

```html
@page "/users"

<h3>User List</h3>

<ul>
@foreach (var user in Users)
{
    <li>@user</li>
}
</ul>

<button @onclick="Reload">Refresh</button>

@code {
    List<string> Users = new() { "Alice", "Bob" };

    void Reload()
    {
        // in a real app you could reload from DB or service
        Users = new() { "Alice", "Bob", "Charlie" };
    }
}
```

