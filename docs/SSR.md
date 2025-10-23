

# SSR (Server Side Rendering)

## Sequence Diagram

```mermaid
sequenceDiagram
participant C as Client (Browser)
participant S as Server
  
C->>S: 1. Send HTTP request (GET or POST)

S->>S: 2. Process request and generate HTML

S->>S: 3. Use template engine (Razor, PHP, etc.)

S-->>C: 4. Return full HTML page

C->>C: 5. Render entire page in browser
```

## 🧩 C# (Razor MVC)

- HTML (`Index.cshtml`)
```html
<h1>User List</h1>

<ul>
@foreach (var u in Model)
{
    <li>@u</li>
}
</ul>
```

- C# (`HomeController.cs`)
```cs
public IActionResult Index()
{
    var users = new[] { "Alice", "Bob" };
    return View(users); // Rendering full page (SSR)

```

- HTML (`List.cshtml`)

```html
<ul><li>Alice</li><li>Bob</li></ul>
```
