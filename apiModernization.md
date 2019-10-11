# API Modernization: Building Bridges As You Cross Them

by Shelley Vohr

## What IS Modernization?

- What does it mean for something to be **modern**?
- Does modernization take the same form across contexts?
- Can we all understand it the same way?

## Why would we even want to modernize?

To **retain** and **extend** the value of a legacy investment, which is an investment that continues to provide core services to an organization.

## Examples from working on the Electron Team

**Electron**: Combines Node.js, Chromium, and Native API's for Windows, Mac, and Linux — allows writing a desktop app once and having it work across operating systems.

### Platform modernization

Operating systems can update API's across major releases — they don't follow semantic versioning.

Example - Apple updated the tray icon API to not allow developer management of highlighting

Learnings - Be more informative and less reactionary

### Language modernization

Example: Updating API's from callback to Promise based contract.

Instead of implementing this in JavaScript, they chose to implement it natively by using the V8 engine, which allowed Promises _and_ callbacks (with added benefit of multi-threading!)

Learnings:

- Deprecating methods well is a non-trivial task
- Be mindful of backwards compatibility
- Ensure documents are up-to-date and clear about differences between versions

### Dependency modernization

Example:

- Upgrading Node is easy - they follow semver, and causes an Electron semver bump
- Chromium is harder, they don't follow semver

Learnings:

- Dependencies won't all hit nicely together, so make version bundling choices well in advance
- Shorten feedback loop for dependencies

## Communication to end-users

Your users might not consider "latest & greatest" to be the same as you! Ensure that you communicate with them far in advance and with a high degree of detail.

### Ensure redundancy

Make breaking changes discoverable and context-rich. Use many discrete points of failure, e.g. deprecation warnings, API documentation, and social media.

### Communicate early

Inform users when a change will take effect, on what versions, and how much work it will take to update.

### Provide context

Why are you making these changes?
How does this benefit them?
How might this hurt them?
How can they prepare?

### Minimize churn

Don't throw users into an endless wheel of churn with every update! Sometimes, the best choice is not to modernize at all (especially if every update is breaking stuff)

## When to NOT modernize?

> The _latest_ is not the same as the _greatest_

Will it increase technical debt? Will it require more work than is worthwhile? Put another way, is the juice worth the squeeze?
