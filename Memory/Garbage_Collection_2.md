## Garbage Collection 2
```
+---------------------+  ← Lower memory address
| Gen 0 Segment       |
+---------------------+
| Gen 1 Segment       |
+---------------------+
| Gen 2 Segment       |
+---------------------+
| Large Object Heap   | (LOH)
+---------------------+
| Pinned Object Heap  | (POH, .NET 5+)
+---------------------+  ← Higher memory address
```

| GC Type         | GC Mode     | Introduced In        | Concurrent Gen 2 GC | Background Gen 2 GC | Parallel Collection | Multi-Heap Support | Use Case / Notes                        |
|------------------|-------------|-----------------------|----------------------|----------------------|----------------------|---------------------|-----------------------------------------|
| Original GC      | Workstation | .NET Framework 1.0    | ❌ No                | ❌ No                | ❌ No                | ❌ No               | Full blocking GC, single-threaded       |
| Original GC      | Server      | .NET Framework 1.0    | ❌ No                | ❌ No                | ✅ Yes               | ✅ Yes              | Full blocking, multiple heaps per core  |
| Concurrent GC    | Workstation | .NET Framework 1.0 SP3| ✅ Yes (Gen 2 only)  | ❌ No                | ❌ No                | ❌ No               | Concurrent Gen 2 for UI responsiveness  |
| Concurrent GC    | Server      | ❌ Not supported      | ❌ N/A               | ❌ N/A               | ❌ N/A               | ❌ N/A              | Server GC never supported this mode     |
| Background GC    | Workstation | .NET Framework 4.0    | ✅ Yes               | ✅ Yes               | ✅ Yes               | ❌ No               | Non-blocking Gen 2, Gen 0/1 still run   |
| Background GC    | Server      | .NET Framework 4.5    | ✅ Yes               | ✅ Yes               | ✅ Yes               | ✅ Yes              | Fully concurrent, scalable              |

# 🧠 .NET GC Modes: Server vs Workstation (TL;DR)

## ✅ Introduced
- **Both Server GC and Workstation GC** were introduced in:
  - **.NET Framework 1.0 (2002)**

## ⚙️ Differences

| Feature            | Workstation GC                 | Server GC                          |
|--------------------|--------------------------------|-------------------------------------|
| Introduced In      | .NET Framework 1.0             | .NET Framework 1.0                  |
| Default For        | Desktop apps (UI)              | ASP.NET / Server apps               |
| GC Heaps           | 1 global heap                  | 1 heap per logical processor        |
| Parallel GC        | ❌ Limited                     | ✅ Fully parallel                   |
| GC Threads         | 1 or few                       | 1 per heap (per core)               |
| Latency            | Low (UI-friendly)              | Higher latency                      |
| Throughput         | Moderate                       | High                                |
| Gen 2 Collections  | Blocking / Concurrent / Background | Blocking / Background         |
| Background GC      | ✅ From .NET 4.0               | ✅ From .NET 4.5                    |

## 🛠 Config (runtimeconfig.json)
```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true
    }
  }
}
