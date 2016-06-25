# Contributing

## Open Test Alliance Contributor License Agreement

**Project License:** [Apache License Version 2.0](LICENSE)

- You will only Submit Contributions where You have authored 100% of the content.
- You will only Submit Contributions to which You have the necessary rights. This means that if You are employed You have received the necessary permissions from Your employer to make the Contributions.
- Whatever content You Contribute will be provided under the Project License(s).

## Pull Requests

Please add the following lines to your pull request description:

```markdown
---

I hereby agree to the terms of the Open Test Alliance Contributor License Agreement.
```

## Coding Conventions

### Formatting

Code formatting is enforced using the [Spotless](https://github.com/diffplug/spotless)
Gradle plugin. You can use `gradle spotlessApply` to format new code and add missing
license headers to source files. Formatter settings for Eclipse are available
[in the repository](https://github.com/ota4j-team/opentest4j/blob/master/etc/eclipse/eclipse-formatter-settings.xml).
For IntelliJ IDEA there's a [plugin](https://plugins.jetbrains.com/plugin/6546) you can use.

### Javadoc

- Javadoc comments should be wrapped after 80 characters whenever possible.
- This first paragraph must be a single, concise sentence that ends with a period (".").
- Place `<p>` on the same line as the first line in a new paragraph and precede `<p>` with a blank line.
- Insert a blank line before at-clauses/tags.
- Favor `{@code foo}` over `<code>foo</code>`.
- Favor literals (e.g., `{@literal @}`) over HTML entities.
- Use `@since 1.0` instead of `@since 1.0.0`.
- Use `@author` tags with full, real names (no nicknames or aliases) at the type level. Do not include email addresses or URLs in `@author` tags.

### Tests

#### Naming

- Tests are written using JUnit 4.
- All test classes must end with a `Tests` suffix.
- Example test classes that should not be picked up by the build must end with a `TestCase` suffix.

#### Assertions

- Use `org.junit.Assert` wherever possible.
- Do not use `junit.framework.Assert`.
- Use AssertJ when richer assertions are needed.

#### Mocking

- Use either Mockito or hand-written test doubles.
