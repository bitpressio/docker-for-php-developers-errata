# Docker for PHP Developers Errata

## Chapter 3

### :warning: Page 26 & 27 - Confusing Example `RUN` Commands

Starting on Page 26 and ending near the top of page 27, the book shows an example of combining multiple commands into one `RUN` instruction, but the `cp` path might confuse users. Instead of the file being at the path `/srv/`, it should be `/srv/app/`.

__Book Contents:__

```bash
# Valid but creates separate layers
RUN cp /srv/.env.example /srv/.env
RUN touch /tmp/foo

# Combines commands into one RUN instruction
RUN cp /srv/.env.example /srv/.env \
    && touch /tmp/foo
```

__Correction:__

```bash
# Valid but creates separate layers
RUN cp /srv/app/.env.example /srv/app/.env
RUN touch /tmp/foo

# Combines commands into one RUN instruction
RUN cp /srv/app/.env.example /srv/app/.env \
    && touch /tmp/foo
```

Although the code only serves an example, it affect the final Dockerfile in the chapter.
