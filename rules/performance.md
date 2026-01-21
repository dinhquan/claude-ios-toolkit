# iOS Performance

- Avoid heavy work on main thread
- Use background queues for IO and parsing
- Cache decoded images and expensive computations
- Minimize SwiftUI view recomputation
- Measure with Instruments before optimizing

Red flags:
- Layout in `body` with heavy work
- Excessive `onAppear` network calls
- Unbounded arrays in memory
