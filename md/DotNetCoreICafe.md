### **1. What is .NET Standard?**  
- .NET Standard is a specification that defines a set of APIs that all .NET implementations must provide.  
- It allows developers to share code across different .NET platforms like .NET Framework, .NET Core, and Xamarin.  
- It simplifies library development by eliminating compatibility issues across platforms.  
- I used .NET Standard in my project to create a shared library for a cross-platform application using .NET Core and Xamarin.  

```csharp
// Shared library in .NET Standard
public class Utility
{
    public string GetMessage() => "Hello from .NET Standard!";
}
```

---

### **2. What is the .NET Framework?**  
- .NET Framework is a Windows-only framework for building and running desktop, web, and enterprise applications.  
- It includes libraries like ASP.NET for web apps and WPF/WinForms for desktop applications.  
- It supports features like garbage collection, type safety, and interoperability with COM components.  
- I worked on an enterprise application using .NET Framework to manage employee data with WPF for the UI.  

```csharp
// Example of a WPF Application
<Button Content="Click Me" Click="Button_Click"/>
```

---

### **3. What is .NET Core?**  
- .NET Core is a cross-platform, open-source framework for building modern applications.  
- It supports multiple OSs, including Windows, Linux, and macOS, and is optimized for cloud and microservices.  
- .NET Core provides improved performance and a modular approach compared to the .NET Framework.  
- I used .NET Core in a project to build a scalable REST API for managing e-commerce transactions.  

```csharp
// Minimal API in .NET Core
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "Hello, .NET Core!");
app.Run();
```

---

### **4. What is the difference between string and String in C#?**  
- Both `string` and `String` refer to the same type in C#; they are aliases for `System.String`.  
- `string` is a C# keyword, while `String` is a .NET class type defined in the `System` namespace.  
- Using `string` is more common in C# coding conventions for declarations, while `String` is used for accessing static methods.  
- I used both in a project to manipulate file paths and content efficiently.  

```csharp
string lower = "hello";
string upper = String.ToUpper(lower);
Console.WriteLine(upper); // Output: HELLO
```

---

### **5. What is Generic Hosting in .NET Core?**  
- Generic Hosting is a framework for building applications with dependency injection, configuration, and logging.  
- It provides a unified way to host applications, including console apps, web apps, and background services.  
- The `HostBuilder` API is used to configure and build the host, which acts as the runtime environment.  
- I used Generic Hosting to host a background service for processing real-time data in a .NET Core application.  

```csharp
var host = Host.CreateDefaultBuilder(args)
    .ConfigureServices(services => services.AddHostedService<MyBackgroundService>())
    .Build();

await host.RunAsync();
```

---

### **6. What do you understand by Value types and Reference types in .NET? Provide some comparison.**  
- Value types store data directly, while reference types store references to their data in memory.  
- Value types are allocated on the stack, whereas reference types are allocated on the heap.  
- Modifying a value type does not affect the original instance; modifying a reference type does.  
- I applied these concepts to optimize memory usage in a performance-critical project.  

```csharp
// Example
int valueType = 10; // Value type
string referenceType = "Hello"; // Reference type
```

---

### **7. What is IoC (DI) Container?**  
- Inversion of Control (IoC) Container manages the lifecycle and dependencies of objects automatically.  
- It decouples components by using dependency injection (DI) to provide required services.  
- Popular IoC Containers in .NET include built-in `Microsoft.Extensions.DependencyInjection`.  
- I implemented an IoC Container in my project to simplify service injection in an ASP.NET Core application.  

```csharp
services.AddScoped<IService, ServiceImplementation>();
```

---

### **8. What is MSIL?**  
- Microsoft Intermediate Language (MSIL) is the CPU-independent code generated by the .NET compiler.  
- It gets converted to native code by the Just-In-Time (JIT) compiler at runtime.  
- MSIL ensures code portability across different architectures supported by .NET.  
- I analyzed MSIL using tools like ILDASM for debugging low-level issues in a project.  

```csharp
// Sample MSIL (simplified)
IL_0001: ldstr "Hello, World!"
IL_0006: call void [mscorlib]System.Console::WriteLine(string)
```

---

### **9. What is .NET Standard and why do we need to consider it?**  
- .NET Standard is a unifying library specification for all .NET implementations.  
- It enables code sharing across different platforms, improving development consistency.  
- It reduces duplication of effort when creating libraries for cross-platform applications.  
- I used .NET Standard for creating a reusable library to handle logging in a multi-platform project.  

---

### **10. Name some CLR services.**  
- Memory management, including garbage collection.  
- Code access security and role-based security.  
- Just-In-Time (JIT) compilation and execution.  
- I leveraged garbage collection and security services in a secure financial application.  

---

### **11. What is a .NET application domain?**  
- Application Domain (AppDomain) isolates applications from one another in the same process.  
- It ensures that faults in one application do not affect others.  
- AppDomains were commonly used in the .NET Framework but are replaced by AssemblyLoadContext in .NET Core.  
- I utilized AppDomains for dynamically loading plugins in a legacy .NET Framework application.  

---

### **12. What is CTS?**  
- Common Type System (CTS) defines how types are declared, used, and managed in .NET.  
- It ensures interoperability between languages supported by the .NET runtime.  
- CTS supports two categories: Value types and Reference types.  
- I worked with CTS to ensure type compatibility between C# and VB.NET components in a project.  

---

### **13. What is CLR?**  
- Common Language Runtime (CLR) is the execution engine of .NET, managing code execution.  
- It handles memory, thread management, and garbage collection.  
- CLR provides cross-language integration and exception handling.  
- I utilized CLR features like garbage collection for memory-efficient processing in a data-heavy project.  

---

### **14. What is an unmanaged resource in .NET?**  
- Unmanaged resources are resources not managed by the CLR, such as file handles or database connections.  
- These resources must be explicitly released to prevent memory leaks.  
- The `IDisposable` interface is used to clean up unmanaged resources.  
- I implemented `Dispose` in a class managing database connections to ensure resource cleanup.  

```csharp
public void Dispose()
{
    connection.Close();
}
```

---

### **15. What is the difference between decimal, float, and double in .NET?**  
- `decimal` is used for high-precision calculations like financial applications.  
- `float` is a single-precision floating-point type with 7 significant digits.  
- `double` is a double-precision floating-point type with 15-16 significant digits.  
- I used `decimal` for calculations in a payroll system to maintain accuracy.  

```csharp
decimal salary = 12345.67m;
float rate = 0.5f;
double pi = 3.14159;
```
### **16. What is Boxing and Unboxing?**  
- Boxing is the process of converting a value type to an object type.  
- Unboxing is converting an object type back to a value type.  
- Boxing and unboxing are costly operations as they involve heap allocation and type conversion.  
- I optimized performance in a project by minimizing boxing operations when working with collections.  

```csharp
int number = 42; // Value type
object boxed = number; // Boxing
int unboxed = (int)boxed; // Unboxing
```

---

### **17. What are some characteristics of .NET Core?**  
- .NET Core is cross-platform, running on Windows, Linux, and macOS.  
- It is modular, with a lightweight runtime and framework libraries.  
- It provides high performance and supports microservices and containers.  
- I used .NET Core in a containerized microservices architecture to build scalable APIs.  

```bash
# Dockerfile for .NET Core application
FROM mcr.microsoft.com/dotnet/aspnet:6.0
COPY ./publish /app
WORKDIR /app
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

---

### **18. What is the difference between .NET Core and Mono?**  
- .NET Core is a modern, cross-platform framework for building applications.  
- Mono is a .NET implementation focused on mobile (Xamarin) and gaming platforms (Unity).  
- Mono provides a broader API surface for older .NET Framework compatibility.  
- I used Mono in a Xamarin project to create a mobile app for iOS and Android.  

---

### **19. What's the difference between SDK and Runtime in .NET Core?**  
- SDK (Software Development Kit) includes tools, libraries, and the runtime for development.  
- Runtime is only for executing .NET applications, without development tools.  
- Developers need the SDK, while end-users need only the runtime to run applications.  
- I ensured the runtime was installed on production servers for running a .NET Core web app.  

---

### **20. What officially replaces WCF in .NET Core?**  
- WCF is replaced by gRPC, which is a modern RPC framework.  
- gRPC supports cross-platform, high-performance communication with features like streaming.  
- Unlike WCF, gRPC uses Protocol Buffers (protobuf) for serialization.  
- I migrated a legacy WCF service to gRPC for improved performance and cross-platform compatibility.  

```csharp
// gRPC Service definition
service Greeter {
  rpc SayHello (HelloRequest) returns (HelloReply);
}
```

---

### **21. What are some benefits of using the Options Pattern in ASP.NET Core?**  
- Centralizes configuration settings in strongly-typed classes.  
- Simplifies validation and management of application settings.  
- Reduces dependency on direct configuration retrieval in the codebase.  
- I used the Options Pattern to manage API keys and other settings in a secure project.  

```csharp
services.Configure<MySettings>(Configuration.GetSection("MySettings"));
```

---

### **22. How can you create your own scope for a Scoped object in .NET?**  
- Use `IServiceScopeFactory` to create a new scope explicitly.  
- Scoped objects are resolved within the lifetime of the created scope.  
- It ensures proper lifecycle management in background tasks or non-HTTP contexts.  
- I used `IServiceScopeFactory` to handle database operations in a background worker service.  

```csharp
using (var scope = scopeFactory.CreateScope())
{
    var dbContext = scope.ServiceProvider.GetRequiredService<MyDbContext>();
    dbContext.SaveChanges();
}
```

---

### **23. Explain the IoC (DI) Container service lifetimes.**  
- Transient: New instance created each time it is requested.  
- Scoped: Instance is created per scope (e.g., per HTTP request in web apps).  
- Singleton: Single instance throughout the application lifecycle.  
- I used Scoped services in an API project to manage database contexts per request.  

```csharp
services.AddScoped<IMyService, MyService>();
```

---

### **24. What is the correct pattern to implement long-running background work in ASP.NET Core?**  
- Use `IHostedService` or its derived class `BackgroundService`.  
- Ensure proper lifecycle management with `StartAsync` and `StopAsync` methods.  
- Use dependency injection to access required services in the background worker.  
- I implemented a `BackgroundService` to process a queue of tasks in a real-time system.  

```csharp
public class MyBackgroundService : BackgroundService
{
    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            // Background task logic
            await Task.Delay(1000);
        }
    }
}
```

---

### **25. What about MVC in .NET Core?**  
- MVC (Model-View-Controller) is a design pattern for building web applications.  
- ASP.NET Core MVC supports routing, dependency injection, and middleware integration.  
- Razor views are used for creating dynamic HTML templates.  
- I developed an e-commerce website using ASP.NET Core MVC for scalable and maintainable code.  

---

### **26. Explain the use of the BackgroundService class in ASP.NET Core.**  
- `BackgroundService` is an abstract base class for implementing long-running background tasks.  
- It simplifies lifecycle management with built-in methods like `ExecuteAsync`.  
- Dependency injection can be used to access services in the background task.  
- I used `BackgroundService` to implement a task scheduler for periodic email notifications.  

---

### **27. What is the difference between .NET Standard and PCL (Portable Class Libraries)?**  
- .NET Standard defines a consistent API set across all .NET implementations.  
- PCL allows targeting multiple platforms but has limited API availability compared to .NET Standard.  
- .NET Standard is easier to maintain and supports more modern frameworks.  
- I replaced a PCL library with .NET Standard to simplify cross-platform library sharing.  

---

### **28. What is JIT Compiler?**  
- The Just-In-Time (JIT) compiler converts MSIL into native machine code at runtime.  
- It optimizes code execution by compiling only the parts that are needed.  
- JIT enables cross-platform execution by adapting to the target machine.  
- I analyzed JIT performance using profiling tools to optimize a high-load application.  

---

### **29. What does Common Language Specification (CLS) mean?**  
- CLS defines a subset of common features that all .NET languages must support.  
- It ensures interoperability between different .NET languages like C# and VB.NET.  
- CLS-compliant code can be reused across any .NET language.  
- I wrote CLS-compliant libraries to ensure compatibility with a VB.NET legacy system.  

```csharp
// CLS-compliant example
public class MyClass
{
    public int Add(int a, int b) => a + b;
}
```

---

### **30. What's the difference between .NET Core, .NET Framework, and Xamarin?**  
- .NET Core is cross-platform and optimized for modern applications.  
- .NET Framework is Windows-only, primarily for legacy applications.  
- Xamarin is for cross-platform mobile and desktop app development.  
- I used Xamarin to develop a single codebase app for Android and iOS.  

### **31. Explain the difference between Managed and Unmanaged code in .NET.**  
- Managed code is executed by the CLR, which handles memory management and security.  
- Unmanaged code is executed directly by the OS and requires manual memory management.  
- Managed code benefits from garbage collection, while unmanaged code relies on `IDisposable` for cleanup.  
- I worked with managed and unmanaged code in a project that required calling native libraries using P/Invoke.  

```csharp
[DllImport("user32.dll")]
public static extern int MessageBox(IntPtr hWnd, string text, string caption, uint type);
```

---

### **32. What is FCL?**  
- Framework Class Library (FCL) is a collection of reusable classes, interfaces, and value types.  
- It provides APIs for common programming tasks like file I/O, data access, and networking.  
- FCL is part of the .NET Base Class Library (BCL) and is included in all .NET implementations.  
- I used FCL to handle file management and database operations in an enterprise app.  

```csharp
using System.IO;
File.WriteAllText("example.txt", "Hello, FCL!");
```

---

### **33. What is Kestrel?**  
- Kestrel is a lightweight, cross-platform web server used in ASP.NET Core.  
- It is built on `libuv` for asynchronous I/O and offers high performance.  
- Kestrel can be used standalone or behind a reverse proxy like Nginx or IIS.  
- I deployed an ASP.NET Core application with Kestrel as the server for high throughput.  

```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();
app.Run();
```

---

### **34. What is the difference between Class Library (.NET Standard) and Class Library (.NET Core)?**  
- Class Library (.NET Standard) is cross-platform and supports multiple .NET implementations.  
- Class Library (.NET Core) is specific to .NET Core and newer .NET versions.  
- .NET Standard is ideal for shared libraries, while .NET Core libraries leverage specific features of .NET Core.  
- I used a .NET Standard library for a logging module shared across .NET Core and Xamarin projects.  

---

### **35. What is Explicit Compilation?**  
- Explicit Compilation compiles source code to a binary format, such as MSIL, before runtime.  
- It contrasts with implicit compilation, where code is compiled on the fly (e.g., Razor views).  
- Explicit Compilation improves performance by reducing runtime overhead.  
- I used explicit compilation to precompile views in an ASP.NET Core MVC app for faster response times.  

```bash
dotnet build
```

---

### **36. Is there a way to catch multiple exceptions at once and without code duplication?**  
- Use a single `catch` block with multiple exception filters.  
- The `when` keyword allows custom logic for filtering exceptions.  
- This approach reduces code duplication and keeps the logic concise.  
- I handled different exceptions with specific actions in a payment processing system.  

```csharp
try
{
    // Code that may throw exceptions
}
catch (InvalidOperationException ex) when (ex.Message.Contains("specific"))
{
    Console.WriteLine("Handle InvalidOperationException");
}
catch (Exception ex)
{
    Console.WriteLine("Handle General Exception");
}
```

---

### **37. What is CoreCLR?**  
- CoreCLR is the runtime for .NET Core, providing execution, garbage collection, and type safety.  
- It is modular and lightweight, designed for high-performance applications.  
- CoreCLR supports Just-In-Time (JIT) compilation and multi-platform execution.  
- I optimized application performance by profiling CoreCLR behavior in a microservices project.  

---

### **38. What is the use of the IDisposable interface?**  
- `IDisposable` defines a method for releasing unmanaged resources explicitly.  
- It is implemented in classes managing file handles, database connections, or other unmanaged resources.  
- The `using` statement ensures proper disposal of resources.  
- I used `IDisposable` to manage database connections in a data-heavy processing application.  

```csharp
using (var connection = new SqlConnection("connection string"))
{
    connection.Open();
    // Database operations
}
```

---

### **39. What is BCL?**  
- Base Class Library (BCL) is a core subset of the .NET Framework Class Library (FCL).  
- It provides essential classes like `System`, `System.IO`, and `System.Collections`.  
- BCL is the foundation for all .NET applications, ensuring consistent functionality.  
- I used BCL classes like `List<T>` and `DateTime` for data handling and scheduling tasks.  

---

### **40. What are the benefits of Explicit Compilation (AOT)?**  
- Ahead-Of-Time (AOT) compilation reduces startup time by precompiling code to native binaries.  
- It eliminates JIT overhead, improving performance and predictability.  
- AOT can produce smaller executables by removing unused code.  
- I leveraged AOT to optimize a .NET Core application for deployment on low-resource devices.  

```bash
dotnet publish -c Release -r linux-x64 --self-contained
```

---

### **41. Explain the difference between Task and Thread in .NET.**  
- Task represents an asynchronous operation, while Thread is a low-level OS resource.  
- Task is managed by the Task Parallel Library (TPL), which optimizes thread usage.  
- Tasks support cancellation and continuation, whereas threads are more static.  
- I used tasks in a data processing project to handle multiple parallel operations efficiently.  

```csharp
Task.Run(() => Console.WriteLine("Running a Task"));
```

---

### **42. When should we use .NET Core and .NET Standard Class Library project types?**  
- Use .NET Standard for libraries shared across multiple .NET platforms.  
- Use .NET Core for libraries leveraging .NET Core-specific features.  
- For cross-platform compatibility, prefer .NET Standard.  
- I used .NET Standard for a logging library and .NET Core for application-specific extensions.  

---

### **43. Explain two types of deployment for .NET Core applications.**  
- Framework-Dependent Deployment (FDD): Requires the runtime to be installed on the target machine.  
- Self-Contained Deployment (SCD): Bundles the runtime with the application, requiring no installation.  
- FDD reduces size, while SCD ensures compatibility.  
- I used SCD to deploy a web app on Linux without worrying about runtime installation.  

---

### **44. Explain what is included in .NET Core.**  
- CoreCLR for runtime execution and garbage collection.  
- CoreFX as the foundational library for .NET Core applications.  
- CLI tools for development and publishing applications.  
- I used these features in a project to develop and deploy a high-performance API.  

---

### **45. What is the difference between .NET Core and .NET Framework?**  
- .NET Core is cross-platform, while .NET Framework is Windows-only.  
- .NET Core is open-source and modular, whereas .NET Framework is monolithic.  
- .NET Core supports modern workloads like microservices and containers.  
- I migrated a legacy .NET Framework app to .NET Core to enable cross-platform support.  

We have completed answers for 45 out of 68 questions. The remaining 23 questions are listed below with answers provided in the same format.

---

### **46. What's the difference between gRPC and WCF?**  
- gRPC is a modern RPC framework, while WCF is a legacy Windows-specific framework.  
- gRPC uses HTTP/2 and Protocol Buffers for performance, while WCF supports various protocols.  
- gRPC is cross-platform; WCF is tied to the .NET Framework and Windows.  
- I replaced WCF with gRPC for a cross-platform microservices project using .NET Core.  

```csharp
// gRPC Service implementation
public class GreeterService : Greeter.GreeterBase
{
    public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
    {
        return Task.FromResult(new HelloReply { Message = "Hello " + request.Name });
    }
}
```

---

### **47. Why does .NET Standard library exist?**  
- .NET Standard provides a consistent API across all .NET platforms.  
- It simplifies sharing code between .NET Framework, .NET Core, and Xamarin.  
- Developers can target multiple platforms with one library.  
- I used .NET Standard to create a shared library for an analytics module reused in mobile and web projects.  

---

### **48. Why shouldn't I use the Repository Pattern with Entity Framework?**  
- EF Core already implements a Unit of Work and Repository pattern.  
- Adding another layer often leads to unnecessary abstraction and complexity.  
- It can result in code duplication and maintenance challenges.  
- I avoided using the Repository Pattern with EF Core and relied on DbContext directly for simplicity.  

```csharp
var products = await _dbContext.Products.ToListAsync();
```

---

### **49. When using DI in Controller, should I call Dispose on any injected service?**  
- No, the DI container manages the lifecycle of injected services.  
- Disposing manually can lead to runtime errors.  
- Scoped and transient services are disposed automatically at the end of the scope.  
- I relied on DI for managing a DbContext's lifecycle in an ASP.NET Core web application.  

---

### **50. Explain how Asynchronous tasks (async/await) work in .NET.**  
- `async` marks a method as asynchronous, enabling non-blocking calls.  
- `await` suspends the method until the awaited task completes.  
- It improves scalability by releasing threads during I/O operations.  
- I implemented async/await in a web API to handle database operations efficiently.  

```csharp
public async Task<IActionResult> GetDataAsync()
{
    var data = await _dbContext.Data.ToListAsync();
    return Ok(data);
}
```

---

### **51. What's the difference between JIT and Roslyn?**  
- JIT compiles MSIL to native code at runtime; Roslyn compiles C# to MSIL at design time.  
- JIT improves runtime performance through optimizations.  
- Roslyn is a compiler-as-a-service for building dynamic .NET applications.  
- I used Roslyn to implement real-time C# code evaluation in a project.  

```csharp
var syntaxTree = CSharpSyntaxTree.ParseText("int x = 10;");
```

---

### **52. What is the difference between IHost, IHostBuilder, and IHostedService?**  
- `IHost` represents the application's lifecycle, including starting and stopping.  
- `IHostBuilder` is used to configure and build an `IHost` instance.  
- `IHostedService` is for long-running background tasks.  
- I used `IHostBuilder` and `IHostedService` to implement a background worker for an email service.  

---

### **53. When to use Transient, Scoped, and Singleton DI service lifetimes?**  
- Transient: Use for lightweight, stateless services needed for each request.  
- Scoped: Use for services tied to a single request or scope.  
- Singleton: Use for services that should persist throughout the application's lifetime.  
- I used Singleton for configuration services in a microservices project.  

---

### **54. What is the difference between Hosted Services vs Windows Services?**  
- Hosted Services run in ASP.NET Core apps, while Windows Services run as standalone services.  
- Hosted Services integrate with the application's lifecycle, Windows Services do not.  
- Windows Services are OS-dependent; Hosted Services are cross-platform.  
- I migrated a Windows Service to a Hosted Service for cross-platform compatibility.  

---

### **55. Explain different types of Inheritance.**  
- Single Inheritance: A class inherits from one base class.  
- Multilevel Inheritance: A class inherits from a derived class.  
- Multiple Inheritance: Not directly supported in C#, but achieved via interfaces.  
- I used multilevel inheritance in a project to manage different layers of functionality.  

```csharp
class Base { }
class Derived : Base { }
```

---

### **56. What is the difference between CIL and MSIL (IL)?**  
- Common Intermediate Language (CIL) and Microsoft Intermediate Language (MSIL) are the same.  
- They represent platform-independent code executed by the CLR.  
- The term CIL is used in ECMA standards, and MSIL is Microsoft's implementation.  
- I debugged MSIL to analyze performance issues in a complex application.  

---

### **57. What are the benefits of using JIT?**  
- JIT optimizes code for the specific runtime environment.  
- It enables platform independence by compiling IL to machine code.  
- Features like inlining and branch optimization improve performance.  
- I leveraged JIT for high-performance scenarios in a CPU-intensive API.  

---

### **58. Explain the Implicit Compilation process.**  
- Implicit Compilation occurs automatically when code changes are detected.  
- Common in dynamic content rendering like Razor pages in ASP.NET Core.  
- Simplifies development by removing manual build steps.  
- I relied on implicit compilation for rapid prototyping of Razor views.  

---

### **59. Why does .NET use a JIT compiler instead of just compiling the code once on the target machine?**  
- JIT allows platform independence by deferring compilation to runtime.  
- It optimizes code based on runtime conditions.  
- Reduces the application size compared to Ahead-Of-Time (AOT) compilation.  
- I used JIT for flexibility while deploying applications on diverse server environments.  

---

### **60. What is the difference between AppDomain, Assembly, Process, and Thread?**  
- AppDomain: Logical container for running .NET code; isolated environment.  
- Assembly: Physical deployment unit containing MSIL.  
- Process: OS-level container for executing an application.  
- Thread: Smallest unit of execution within a process.  
- I managed threads for parallel data processing in a multithreaded app.  

---

### **61. Does .NET support Multiple Inheritance?**  
- No, .NET does not support multiple inheritance with classes.  
- It supports multiple inheritance using interfaces.  
- This avoids complexity and ambiguity in method resolution.  
- I implemented multiple inheritance using interfaces to define modular components.  

```csharp
interface IShape { void Draw(); }
interface IColor { void Paint(); }
class Square : IShape, IColor { }
```

---

### **62. What is the difference between .NET Framework/Core and .NET Standard Class Library project types?**  
- .NET Framework/Core libraries are tied to specific platforms.  
- .NET Standard libraries ensure compatibility across multiple .NET implementations.  
- .NET Core libraries can leverage platform-specific features; .NET Standard cannot.  
- I chose .NET Standard for libraries shared across web and mobile apps.  

---

### **63. How to choose the target version of .NET Standard library?**  
- Select the version based on the minimum framework that supports your target platforms.  
- Higher versions include more APIs but have limited platform support.  
- Consider .NET Standard 2.0 for broad compatibility.  
- I targeted .NET Standard 2.0 to support both .NET Framework 4.6.1 and .NET Core 2.0.  

---

### **64. Could you name the difference between .NET Core, Portable, Standard, Compact, UWP, and PCL?**  
- .NET Core: Cross-platform, modern, modular.  
- Portable Class Libraries (PCL): Limited API, legacy compatibility.  
- .NET Standard: Unified API for all .NET platforms.  
- Compact: For devices with limited resources, deprecated.  
- Universal Windows Platform (UWP): For Windows 10 apps.  
- I migrated a PCL library to .NET Standard for better compatibility and maintainability.  

---

### **65. Explain when to use Finalized vs Dispose.**  
- Finalize: Used for unmanaged resource cleanup, called by the garbage collector.  
- Dispose: Explicit resource cleanup, called manually or via `using`.  
- Implement both in cases where unmanaged resources must be handled.  
- I implemented both in a class managing database connections and file streams.  

```csharp
public void Dispose() { /* Cleanup */ }
~MyClass() { /* Finalizer Logic */ }
```

---

### **66. Explain some deployment considerations for Hosted Services.**  
- Ensure proper configuration for lifecycle management.  
- Use scoped services to handle DI.  
- Plan for resource cleanup and graceful shutdown.  
- I deployed a Hosted Service to manage periodic data sync tasks in a distributed system.  

---

### **67. How many types of JIT Compilations do you know?**  
- Pre-JIT: Compiles entire code during application deployment.  
- Econo-J

IT: Compiles methods as they are called with minimal optimization.  
- Normal-JIT: Compiles methods on demand with full optimization.  
- I used Normal-JIT to balance startup performance and runtime efficiency.  

---

### **68. What are some differences between X86, AnyCPU, and X64 compilations?**  
- X86: Compiled for 32-bit platforms.  
- X64: Compiled for 64-bit platforms.  
- AnyCPU: Runs on both but defaults to 64-bit if available.  
- I compiled a project with AnyCPU to ensure compatibility across diverse environments.  

--- 

