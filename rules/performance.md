# iOS Performance

## Core Rules
- Avoid heavy work on the main thread.
- Offload IO, JSON decoding, and image processing.
- Cache decoded images and expensive computations.
- Use Instruments before optimizing.

## SwiftUI Specific
- Keep `body` lightweight.
- Avoid repeated work in `onAppear`.
- Use `task` with cancellation where possible.
- Extract subviews to reduce recomputation.

## Red Flags
- Layout work or parsing in `body`.
- Excessive `onAppear` network calls.
- Unbounded arrays or caches in memory.
- Long-running tasks without cancellation.
