### 0.0.1

Initial release

- Introduce `Poll` module for generic polling
- Introduce `Dir` module for common directory integration test operations

### 1.0.0

- Introduce `Item` module for common file integration test operations
- Introduce `Http` module for common http integration test operations
  - Starting a HTTP endpoint on a given url
  - Route received HTTP requests to custom handlers
  - Collecting several HTTP requests until expected count
- Introduce `Log` module for centrilized logging

### 1.2.1

- Add polling shortcuts:
  - `Poll.targetSync` for polling at "sync" targets (ex. filesystem)
  - `Poll.file`, `Poll.dir` & `Poll.http_*` for shortcutting common targets
  - `Poll.untilAny`, `Poll.untilLength`, `Poll.untilContains`, ... for shortcutting sequence filters
  - `Poll.untilEqual` & `Poll.untilNotEqual` for shortcutting simple equalization
- Adding more logging information and customization:
  - `Poll.errorf` for custom string formatting the error message for the polling (also available in the `PollBuilder` Computation Expression)
- Adding HTTP simulation:
  - `Http.simulate(s)` for simulating a series of HTTP responses for the same hosted HTTP server (ex. for testing retryable operations)
- Adding IO operations:
  - `Dir.move(Undo)`, `Item.move(Undo)` for moving directories/files with and reverting on disposal

### 1.5.0

- Add polling shortcuts:
  - `Poll.untilEmpty` for shortcutting sequence filters
  - `Poll.untilTrue` & `Poll.untilFalse` for shortcutting boolean targets
- Add HTTP shortcut `Http.receive` for simple receival of a single HTTP request
- Add polling alternatives with `Poll.orElse`, `Poll.orElseWith`, `Poll.orElseAsync` and `Poll.orElseValue` when a polling sequence times-out
- Make the remaining C# HTTP server calls (ex. `Http.Serverxxx`) obsolete by removing the `Server` prefix