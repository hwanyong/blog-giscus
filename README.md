# blog-giscus

Comments for [blog.hwanyong.com](https://blog.hwanyong.com).

Each discussion in the **Announcements** category is one comment thread of the
[giscus](https://giscus.app) widget on that site. The site's own source is not in
this repository.

## Why the comments are kept apart from the site

giscus reads and writes discussions through the public GitHub API, and its
configuration page states the requirement: "The repository is public, otherwise
visitors will not be able to view the discussion." The site repository is
private, so its comments are stored here instead.

## A thread's title is `data-term`, not a URL

The site sets giscus `data-mapping` to `specific` and builds the term from an
entry's identity rather than its address:

| Term | Which pages share it |
|---|---|
| `log:first-post` | `/log/first-post/` and `/ko/log/first-post/` |
| `project:analysis-video` | every revision of that series, in both languages |
| `lecture:linear-algebra:01-vectors` | that session, in both languages |

One thread therefore serves both locales and every revision of the same entry,
and an entry that moves to a new address keeps its comments.
**Renaming a discussion detaches it from the page it belongs to.**

## Threads are opened by the app

The Announcements category uses the Announcement discussion format, so only the
maintainer and the giscus app can start a thread. The app opens one the first
time a visitor comments on a page. Threads started by hand would sit next to the
comment threads without belonging to any page.

## `giscus.json`

That file restricts which origins may load the widget. giscus.app reads it from
this repository's root through the GitHub API, which is why it lives here rather
than in the site build.
