# Float16 on Intel Macs

This package enables `Float16` from the Swift Standard Library on Intel Macs. The floating-point type is available on Linux and Windows with x86_64, but not on macOS. ARM64 creates a stable function calling convention when compiling with `-enable-library-evolution`, letting Apple officially port `Float16` to iOS and M1 Macs. However, Intel has a unique calling convention that creates ABI instability.

## How to Use

```swift
#if ((os(macOS) || targetEnvironment(macCatalyst)) && arch(x86_64))
import Float16Module
#endif

print("\(Double(2)) is a Double.")
print("\(Float(2)) is a Float.")
print("\(Float16(2)) is a Float16.")
```
