# snorlaxse-hexo-blog

Hexo blog source for `snorlaxse.github.io`.

## Repository Roles

- `snorlaxse-hexo-blog`: blog source repository. Edit posts, theme, and Hexo config here.
- `snorlaxse.github.io`: generated static site repository. Hexo deploys `public/` output there.

## Common Commands

Install dependencies:

```bash
npm install
```

Preview locally:

```bash
npm run server
```

Clean generated files:

```bash
npm run clean
```

Build static files:

```bash
npm run build
```

Deploy to `snorlaxse.github.io`:

```bash
npm run deploy
```

Recommended publish flow:

```bash
npm run clean
npm run build
npm run deploy
```

## Writing Posts

Create a new post:

```bash
npx hexo new post "Post Title"
```

Post source files live in:

```text
source/_posts/
```

After editing posts, preview locally with `npm run server`, then publish with the recommended publish flow above.

## Git Workflow

Commit source changes in this repository:

```bash
git status
git add .
git commit -m "Update blog"
git push
```

Deployment is handled separately by `npm run deploy`, which publishes generated static files to `git@github.com:snorlaxse/snorlaxse.github.io.git`.
