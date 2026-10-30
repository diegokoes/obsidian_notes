# HOME

## DOMAINS
- [[tech|Tech]]: programming, CS, systems, networking, security
- [[math|Math]]
- [[history|History]]
- [[college|College]]: courses (logistics, evaluation, exercises, exam prep)

## HOW THIS VAULT WORKS
- **Folders = domain only** (`tech/`, `math/`, `history/`, `college/<COURSE>/`). Topic structure lives in hub notes and the `up:` property, not in folders.
- **Names are `prefix_topic`**, lowercase snake_case. The prefix is the parent hub, and the hub is the bare prefix: `java_streams` → `java` → `tech`.
- **Create notes from their hub**: type `[[net_osi_model]]` in `net`, click it, and the template fills `up` and the header.
- **Root = inbox**: anything at the root besides `home` and `README` is waiting to be sorted.
- **Course theory goes to the domain folder** (e.g. `math/`), and the course hub links to it.

## INBOX
```base
filters:
  and:
    - 'file.ext == "md"'
    - '!file.path.contains("/")'
    - 'file.name != "home"'
    - 'file.name != "README"'
views:
  - type: table
    name: Inbox
    order:
      - file.name
      - file.mtime
```

## STUBS
```base
filters:
  and:
    - 'file.ext == "md"'
    - 'file.size < 400'
    - 'file.path.contains("/")'
    - '!file.inFolder("Templates")'
views:
  - type: table
    name: Stubs
    order:
      - file.name
      - up
      - file.size
    sort:
      - property: up
        direction: ASC
```

## RECENT
```base
filters:
  and:
    - 'file.ext == "md"'
    - '!file.inFolder("Templates")'
views:
  - type: table
    name: Recent
    limit: 15
    order:
      - file.name
      - up
      - file.mtime
    sort:
      - property: file.mtime
        direction: DESC
```
