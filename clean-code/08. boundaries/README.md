# Boundaries
Good software design accomodate change without huge investments and rework. Change happens a lot at boundaries.
## Third-party code
- There is a natural tension between an interface's provider and its user: providers strive for broad applicability, users want it tailored to meet their needs
- Use learnings tests to conduct precise experiments about third-party code, separate learning from integration and assert that code stills works after version upgrades
- Write interfaces you wished you had, use the adapter pattern, only use what you need

