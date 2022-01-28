# Events
https://docs.microsoft.com/en-us/dotnet/csharp/events-overview
- Late binding
- Built on delegates
- Way to broadcast to interested parties something has happened

## Design goals
- Minimal coupling between event source and sink
- Simple to un/subscribe
- Support for 0..* subscribers

## Language Support
``` public event EventHandler<FileListArgs> Progress; ```
- EventHandler typically
   - Void
   - Verb/phrase
 - Invocation
 ``` Progress?.Invoke(this, new FileListArgs(file)); ```
