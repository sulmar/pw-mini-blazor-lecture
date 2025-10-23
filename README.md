# 🧭 Blazor — Lecture Roadmap

A structured journey from **fundamentals** to **design patterns** in Blazor.

---

## 🟦 1. Fundamentals

### 🔹 Introduction
- Overview of modern web development with .NET  
- Why Blazor?  
- Blazor as part of the ASP.NET Core ecosystem  

---

### 🔹 What is Blazor
- .NET web framework for interactive UI  
- Components (`.razor` files), state, event handling  
- Example: simple Counter component  
- Key idea: *“Write C#, run in the browser”*  

---

## 🟧 2. Hosting Models

### 🔸 Blazor Server
- Components execute on the **server**  
- DOM updates sent to browser via **SignalR**  
- Centralized state and security  
- Advantages & limitations  

---

### 🔸 SignalR
- Real-time communication between browser and server  
- Persistent WebSocket (or fallback) connection  
- Transfers **UI diffs** and **event messages**  
- Core part of Blazor Server architecture  
- Supports WebSockets, SSE, and long polling  

---

### 🔸 Blazor WebAssembly
- Components execute **client-side** in the browser  
- .NET assemblies compiled to **WebAssembly (WASM)**  
- Works offline, independent from the server  
- Trade-offs: startup time, performance, download size  

---

### 🔸 What is WebAssembly
- Low-level binary format for browsers  
- Runs at near-native speed in a sandbox  
- Supported by all major browsers  
- Languages: C/C++, Rust, Go, C# (via .NET)  
- `.wat` text format uses **S-expressions**

---

## 🟪 3. Design Patterns in Blazor

### 🟩 Composite Pattern
- Component hierarchy = tree structure  
- Parent components contain child components  
- All implement a common interface (`IComponent`)  

---

### 🟦 Observer Pattern
- Components observe state changes  
- `StateHasChanged()` notifies renderer  
- UI updates automatically  

---

### 🟥 Proxy Pattern
- Used in **Blazor Server**  
- Renderer acts as a proxy between browser DOM and server-side logic  
- Communication via SignalR  

---

### 🟨 Adapter Pattern
- `IJSRuntime` bridges .NET and JavaScript  
- Allows seamless JS interop from C#  
- Unifies two incompatible environments  

---

## 🧩 Summary

| Topic | Core Concept |
|--------|---------------|
| **Blazor Fundamentals** | .NET UI framework running in browser |
| **Blazor Server** | Server execution, SignalR connection |
| **Blazor WebAssembly** | Client execution via WebAssembly |
| **WebAssembly** | Binary format for high-performance web apps |
| **Composite** | Tree of components |
| **Observer** | Reactive UI updates |
| **Proxy** | Remote DOM synchronization |
| **Adapter** | JS interop abstraction |

---

> 🎓 **Goal:** Understand how Blazor merges classical software design patterns with modern browser technology.