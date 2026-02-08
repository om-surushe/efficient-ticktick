# Publishing Guide

Due to npm's 2FA requirements, publishing must be done manually.

## Prerequisites

- npm account with publish access to `@omsurushe/efficient-ticktick`
- 2FA enabled on npm account
- Logged in: `npm login`

## Publishing a New Version

1. **Update version in package.json**
   ```bash
   npm version patch  # or minor, or major
   ```

2. **Build the package**
   ```bash
   npm run build
   ```

3. **Publish with 2FA**
   ```bash
   npm publish --access public --otp=YOUR_6_DIGIT_CODE
   ```
   
   Get the OTP code from your authenticator app right before running.

4. **Push git tag**
   ```bash
   git push && git push --tags
   ```

## Version Bumps

- **Patch** (0.1.0 → 0.1.1): Bug fixes
- **Minor** (0.1.0 → 0.2.0): New features, backward compatible
- **Major** (0.1.0 → 1.0.0): Breaking changes

## Checklist Before Publishing

- [ ] All tests pass (`npm test`)
- [ ] Build works (`npm run build`)
- [ ] CHANGELOG.md updated
- [ ] Version bumped in package.json
- [ ] Git committed and pushed
- [ ] 2FA code ready

## Example Full Flow

```bash
# Update version
npm version patch

# Rebuild
npm run build

# Publish (get 2FA code ready!)
npm publish --access public --otp=123456

# Push to GitHub
git push && git push --tags
```
