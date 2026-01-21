# Meragix

High-Performance Software Engineering for the Dart & Flutter Ecosystem.

## Why Meragix Exists

As a full-stack developer building Flutter applications day in and day out, I kept running into the same frustrations: reinventing authentication flows, managing server state, validating data, and dealing with dependency health issues. Instead of copying boilerplate code between projects or settling for incomplete solutions, I decided to build the tools I wish existed.

**This is my daily toolkit**. If a package is here, it's because I depend on it. If it breaks, my apps break. This personal stake means you can trust that:

- **Long-term commitment** - These aren't throwaway projects. I'm invested for the long haul.
- **Real-world tested** - Every feature exists because it solved an actual problem in production.
- **Actively maintained** - I use these packages daily, so bugs get fixed fast.
- **Evolution over revolution** - Breaking changes are minimized because they affect my own projects too.

## Principles

- **Developer Experience First** - Intuitive APIs that feel natural
- **Performance Matters** - Zero unnecessary overhead
- **Documentation Driven** - Every feature is well-documented
- **Test Coverage** - Reliability through comprehensive testing
- **Community Powered** - Built with and for the community
- **Production-First** - No vaporware, only tools that work in real applications

## Packages

### Zema

> Zod-like schema validation for Dart

Runtime type validation with TypeScript-like developer experience.

Features:
- [ ] 🚀 Zero-Allocation Engine
- [ ] ✅ Fluent validation API
- [ ] 🎯 Inferential Type Safety
- [ ] 🧩 Composition over Inheritance
- [ ] 📝 Custom error messages

```dart
import 'package:zema/zema.dart';

final userSchema = z.object({
  'name': z.string().min(2),
  'email': z.string().email(),
  'age': z.number().positive().optional(),
});

// Type-safe parsing
final user = userSchema.parse(data);
print(user.name); // String guaranteed
```

### Qora

> Typed server-state management for Dart with caching & sync

Qora Inspired by TanStack Query, Qora handles server-state complexity with elegance.

Features:
- [ ] 🔄 Automatic background refetching
- [ ] 💾 Smart caching with TTL
- [ ] 🔌 Offline-first support
- [ ] 🎯 Type-safe queries and mutations
- [ ] ⚡ Deduplication & request batching

```dart
import 'package:qora/qora.dart';

qora.fetch<User>(
  ['profile', 123],                      // 1. A unique ID (Key) to remember this data
  queryFn: (signal) => api.getUser(123), // 2. The actual API call
  decoder: (json) => User.fromJson(json) // 3. How to transform JSON into a real Object
  options: QoraOptions(
    staleTime: 5.minutes,
    retryCount: 3,
  ),
);

QoraBuilder<User>(
  queryKey: ['profile', 123], // Qora knows exactly which data to watch
  builder: (context, state) {
    // Qora tells you exactly what is happening:
    if (state.isLoading) return Text("Loading..."); 
    if (state.hasError)  return Text("Offline or Server Error");
    
    return Text("Welcome, ${state.data.name}!");
  },
)
```

###

**Meragix** is not a collection of experimental tools.
Every package exists because it has been used, tested, and refined in real-world applications.
Philosophy
Meragix follows a simple principle:
Build tools that you can trust today, and still rely on years from now.
This ecosystem is shaped by production constraints, not trends.
Design decisions are guided by maintainability, clarity, and long-term stability.
Core principles:
Stability over novelty
Features are introduced only when they solve real problems.
Explicit and predictable APIs
No magic, no hidden behaviors.
Composable architecture
Packages are independent but designed to work seamlessly together.
Production-first mindset
Every tool is built and evolved through real application usage.
Long-Term Commitment
Meragix is built for the long run.
All packages in this ecosystem:
are actively used in production
evolve based on real feedback and constraints
prioritize backward compatibility
avoid unnecessary breaking changes
are documented and versioned carefully
The goal is not to publish many packages, but to maintain a small, coherent, and dependable ecosystem.
This is not vibe code.
It is infrastructure.

## Ecosystem Overview

| Package  | Role | Description |
|----------|--------|-------------|
| **Zema** | Validation | Ultra-fast, Zod-inspired schema validation for Dart. |
| **Qora** | Data | Reactive server-state management and intelligent caching. |
| **Authyra** | Security | Unified authentication framework for Flutter. |
| **Cura** | Audit | Project health sentry and dependency vulnerability auditor. |

Package Role Description Status
Authyra Security  🛠 WIP
Qora Data  🛠 WIP
Cura Audit Project health sentry and dependency vulnerability auditor.

Domain
Package
Description
Authentication & Security
Authyra
Session management, authentication flows, guards, and security primitives.
Data Fetching / Server State
Qora
Declarative data fetching, caching, and server-state management inspired by proven patterns.
Validation
Zema
Strong and composable data validation for client and server logic.
Audit & Monitoring
Lyra
Logging, auditing, and monitoring tools for application visibility.
Utilities
Axo
Core utilities, helpers, and extensions used across the ecosystem.
Each package can be used independently or combined to form a complete foundation.Package Design Rules
All Meragix packages follow the same internal rules:
minimal dependencies
clear separation of concerns
predictable lifecycle and behavior
consistent naming and structure
no hidden global state
If a feature cannot be implemented cleanly, it does not belong in the package.
Who This Is For
Meragix is designed for developers who:
build applications meant to last
care about architecture and maintainability
prefer clear abstractions over clever tricks
want tools that evolve carefully instead of constantly changing
If you are building serious Flutter applications, Meragix aims to be a reliable foundation.
Contribution
Contributions are welcome, but quality always comes first.
Before submitting a change:
Make sure it solves a real, well-defined problem
Keep APIs explicit and stable
Avoid introducing breaking changes
Include documentation and tests when relevant
The ecosystem grows intentionally, not rapidly.
Status
Meragix is actively maintained and evolving as part of real production work.
Updates are driven by usage, not by release schedules.
Closing Note
Meragix is not about reinventing Flutter.
It is about providing solid, dependable building blocks that respect developers’ time and projects.
Meragix — Foundations for Flutter applications that are built to last.

High-Performance Software Engineering for the Dart & Flutter Ecosystem.
Meragix is an open-source development studio dedicated to building robust, modular, and extremely high-performance tools. Our mission is to provide Flutter developers with a unified "Core Stack," eliminating architectural complexity so you can focus on building great user experiences.

## Our Vision

The Meragix philosophy is built on three core pillars:

1. **Total Consistency**: Tools that share the same design language, syntax, and seamless integration.
2. **Raw Performance**: Every package is optimized to minimize memory footprint and maximize execution speed.
3. **Developer Experience (DX)**: Intuitive, type-safe APIs with documentation that leaves no room for doubt.

## Contact & Support

For security vulnerabilities or professional inquiries, please reach out to:
meragix.oss@gmail.com (or via GitHub Discussions).

## License
The entire Meragix ecosystem is released under the **MIT License**. You are free to use it for personal or commercial projects.

_Powered by passion. Maintained by [DonFreddy](https://github.com/donfreddy) and the Meragix community._

<!--

| Package  | Domaine | Description |
|----------|--------|-------------|
| **Axo** | Core / Utils | Primitives, helpers et fondations partagées de l’écosystème. |
| **Zema** | Validation | Validation composable et explicite des données et des entrées. |
| **Qora** | Data / Fetch | Data fetching, cache et gestion du server state. |
| **Authyra** | Auth / Security | Authentification, sessions et protections applicatives. |
| **Specra** | Audit / Observability | Logging, audit et observabilité des flux applicatifs. |

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
