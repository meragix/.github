# Meragix

High-Performance Software Engineering for the Dart & Flutter Ecosystem.

## Vision

Meragix isn't a collection of weekend experiments or quick hacks. These packages are battle-tested solutions born from real-world problems I've encountered over years of Flutter development. Every package in this ecosystem is currently being used in production applications I actively maintain and develop.

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

await qora.fetch<User>(
  ['user', id],
  queryFn: () => api.getUser(id),
  decoder: (json) => User.fromJson(json),
  options: {
    staleTime: Duration(minutes: 5),
  }
);
```

### Authyra

> NextAuth.js-inspired authentication framework for Flutter

A unified, extensible, and ready-to-use authentication solution for mobile, web, and desktop applications.

Features:
- [ ] 🔐 Multiple auth providers (OAuth, Email/Password, Magic Links)
- [ ] 🎯 Type-safe session management
- [ ] 🔄 Auto-refresh tokens
- [ ] 📱 Cross-platform support
- [ ] 👥 Native Multi-Account Support

```dart
import 'package:authyra/authyra.dart';

// Simple, powerful authentication
await Authyra.instance.signIn(
  provider: 'email',
  credentials: {'email': 'user@app.com', 'password': '***'},
);
```

### Cura

> Smart health audit tool for Flutter dependencies

Keep your Flutter project healthy by auditing dependencies and detecting issues.

Features:
- [ ] ⚖️ Legal Compliance Audit
- [ ] 💡 Intelligent Alternative Engine
- [ ] 🛡️ Real-time Security Guard
- [ ] 📊 Smart Cura Scoring
- [ ] 🤖 CI/CD integration

```dart
# Run audit
dart run cura audit

# Check specific package
dart run cura check http
```

## Contributing

We welcome contributions from the community! Whether it's bug reports, feature requests, or pull requests, every contribution helps make Meragix better.

### How to Contribute

1. **Fork the repository** you want to contribute to
2. **Create a feature branch** (git checkout -b feature/amazing-feature)
3. **Make your changes** with clear, descriptive commits
4. **Write/update tests**  to cover your changes
5. **Update documentation** if needed
6. **Submit a pull request**

### Development Guidelines

#### Code Style

- Follow the Effective Dart style guide
- Use dart format before committing
- Keep functions small and focused
- Write self-documenting code with clear naming

#### Testing

- Write unit tests for all new features
- Maintain or improve code coverage
- Test edge cases and error scenarios
- Run dart test before submitting PR

#### Documentation

- Update README.md with new features
- Add inline documentation for public APIs
- Include usage examples
- Update CHANGELOG.md following [Keep a Changelog](https://keepachangelog.com)

#### Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org):
```
feat: add OAuth provider for GitHub
fix: resolve token refresh race condition
docs: update authentication examples
test: add tests for edge cases
```

#### Reporting Issues

When reporting bugs, please include:
- Package name and version
- Dart/Flutter version
- Steps to reproduce
- Expected vs actual behavior
- Code sample (if applicable)

## Community
- **GitHub Discussions**: Ask questions and share ideas
- Discord: Join our Discord server (coming soon)
- Twitter: Follow @meragix for updates (coming soon)

### Contributors

Thanks to all the amazing people who contribute to Meragix!
�

📄 License
All Meragix packages are licensed under the .

###

**Meragix** is not a collection of experimental tools.
Every package exists because it has been used, tested, and refined in real-world applications.
Philosophy
Meragix follows a simple principle:
Build tools that you can trust today, and still rely on years from now.
This ecosystem is shaped by production constraints, not trends.
Design decisions are guided by maintainability, clarity, and long-term stability.

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
