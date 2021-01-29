# Contributing

[T](https://guide.infinitybotlist.com)his guild was made by [mental\#2090](https://infinitybotlist.com/profile) and with the help of the whole of InfinityBotList's team!

This site contains both public-facing usage documentation and internal implementation documentation intended for contributors. As such, the pages are divided into two navigation trees: those under `/docs/internal/` and the remainder under the docs root \(`/docs/`\). Each appears separately on the side nav to the left.

### File format

#### Frontmatter

```text
// Titles
title: Primary page title (appears in <h1> at top) [Required]
shortTitle: Secondary page title (appears in tab title; falls back to title)
overrideNav: Side nav title (falls back to title)
overrideBreadcrumb: Breadcrumb segment title (falls back to shortTitle)

// Switches
noTOC: Disables a table of contents on the right side
noBreadcrumb: Disables the breadcrumb bar at the top
isRoot: Whether this page should form the root of a subtree
  (appear as its own top-level heading in the side nav)

// Misc
childrenOrder: Used to specify explicit ordering of direct children pages (by slug)
```

Page content can be specified using standard markdown format, with additional [MDX elements](https://guide.infinitybotlist.com/contributions/authoring/#mdx-elements) available to enhance docs layout and semantics.

#### Page Generation

Docs pages are generated for each path segment in the entire navigation tree created by all docs `.md` pages. This means that if, for example, there were 2 markdown files in the `/docs` folder:

```text
/docs/
├── pathA/
│   └── pathB/
│       └── index.md
└── index.md
```

Then, there would be **three generated docs pages**: `/`, `/pathA/`, and `/pathA/pathB/`. In this case, `/pathA/` would be designated as an _orphan page_ because it doesn’t have a corresponding markdown file for content. In this mode, it will only contain an auto-generated title from the path segment as well as an [In This Section `<Overview>`](https://guide.infinitybotlist.com/contributions/authoring/#overview) component.

### Headings

```text
# h1 - Lorem ipsum

## h2 - Lorem ipsum

### h3 - Lorem ipsum

#### h4 - Lorem ipsum

##### h5 - Lorem ipsum

###### h6 - Lorem ipsum
```

## h1 - Lorem ipsum

### h2 - Lorem ipsum

#### h3 - Lorem ipsum

**h4 - Lorem ipsum**

**H5 - LOREM IPSUM**

**h6 - Lorem ipsum**

### Elements

#### Blockquote

```text
> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent elementum egestas pretium.
> Proin laoreet arcu et scelerisque facilisis. In hac habitasse platea dictumst. Curabitur ut
> eleifend dui. Morbi eu congue ipsum. Proin fermentum dui hendrerit, mattis ligula id,
> pharetra lacus. Pellentesque sodales nibh et auctor maximus. Donec sed mauris odio. 
```

> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent elementum egestas pretium. Proin laoreet arcu et scelerisque facilisis. In hac habitasse platea dictumst. Curabitur ut eleifend dui. Morbi eu congue ipsum. Proin fermentum dui hendrerit, mattis ligula id, pharetra lacus. Pellentesque sodales nibh et auctor maximus. Donec sed mauris odio.

#### Lists

```text
- Unordered
- list
```

* Unordered
* list

```text
1. Ordered
2. list
```

1. Ordered
2. list

#### Code Block

```text
```py
async def all_guilds(self):
    """Return information about all guilds that the bot is in, including their admins"""
    guilds = []
    for shard, shard_store in self.store.items():
        guilds += shard_store.get('guilds', ())
    return guilds
```
```

```text
async def all_guilds(self):
    """Return information about all guilds that the bot is in, including their admins"""
    guilds = []
    for shard, shard_store in self.store.items():
        guilds += shard_store.get('guilds', ())
    return guilds
```

**Inline Code Block**

```text
`src/manager/app.py` is the main application file for the shard manager
```

`src/manager/app.py` is the main application file for the shard manager

### MDX elements

To auto-generate docs pages, the site uses [MDX](https://github.com/mdx-js/mdx) under the hood to render Markdown content with custom React components. With that in mind, there are a few components that are available to page authors.

To add new ones, a component can be authored and then included in the MDX scope file.

#### Routes

**Restful API Routes**

```text
<Route method="METHOD" path="/route/{parameter}/segment" auth />
```

v1 RESTful API

#### METHOD/route/{parameter}/segment

Requires authentication

**Gateway API Routes**

```text
<GatewayRoute
  eventName="request_elevation"
  room="<SID>"
  sentFrom="client"
  requiresElevation
  payload={{
    token: {
      type: "string",
      description: "Authentication Token"
    }
  }}
/>
```

v1 Gateway API

**EVENT NAME**

**request\_elevation**

**ROOM**

**&lt;SID&gt;**

**Sent from: client**

Requires elevation

**PAYLOAD SCHEMA**

| KEY | TYPE | DESCRIPTION |
| :--- | :--- | :--- |
| token | string | Authentication Token |

#### Overview

The `<Overview>` component can be used to provide an overview of a page’s children in the navigation tree.

```text
<Overview />
```

### In This Section

* [Auto Responses](https://guide.infinitybotlist.com/internal/modules/auto-responses/)
* [Settings](https://guide.infinitybotlist.com/internal/modules/settings/)

#### Demo

The Demo component can be used to show a source/result relationship, which is prevalent throughout the authoring page to demonstrate MDX/markdown features.

```text
<Demo>

~~~md
## Lorem ipsum

Etiam blandit diam sit amet pharetra pellentesque. Integer auctor nisl et sodales
imperdiet. Integer vitae tincidunt augue. Duis condimentum lectus at tincidunt
vehicula. Maecenas ultricies erat id nunc tempus, malesuada accumsan justo
dignissim. Nam interdum vitae arcu et pharetra. Integer eget faucibus arcu.
~~~

<div>

## Lorem ipsum

Etiam blandit diam sit amet pharetra pellentesque. Integer auctor nisl et sodales
imperdiet. Integer vitae tincidunt augue. Duis condimentum lectus at tincidunt
vehicula. Maecenas ultricies erat id nunc tempus, malesuada accumsan justo
dignissim. Nam interdum vitae arcu et pharetra. Integer eget faucibus arcu.

</div>
</Demo>
```

```text
## Lorem ipsum

Etiam blandit diam sit amet pharetra pellentesque. Integer auctor nisl et sodales
imperdiet. Integer vitae tincidunt augue. Duis condimentum lectus at tincidunt
vehicula. Maecenas ultricies erat id nunc tempus, malesuada accumsan justo
dignissim. Nam interdum vitae arcu et pharetra. Integer eget faucibus arcu.
```

### Lorem ipsum

Etiam blandit diam sit amet pharetra pellentesque. Integer auctor nisl et sodales imperdiet. Integer vitae tincidunt augue. Duis condimentum lectus at tincidunt vehicula. Maecenas ultricies erat id nunc tempus, malesuada accumsan justo dignissim. Nam interdum vitae arcu et pharetra. Integer eget faucibus arcu.

#### Alerts

Alerts are a block-level wrapper element that can be used to give emphasis or semantic information to a block of content depending on the _type_ of alert used.

```text
<Alert type="info">

**Informative** content here, such as general tips or bits of info

</Alert>
```

**Informative** content here, such as general tips or bits of info

```text
<Alert type="warning">

**Cautious** content here, such as general warnings against bad practices or incorrect usage

</Alert>
```

**Cautious** content here, such as general warnings against bad practices or incorrect usage

```text
<Alert type="error">

**Error** content here, such as important scenarios to avoid or errors that might occur in the
process

</Alert>
```

**Error** content here, such as important scenarios to avoid or errors that might occur in the process

```text
<Alert type="success">

**Success** content here, such as success scenarios or ways to tell if an action was
successful

</Alert>
```

**Success** content here, such as success scenarios or ways to tell if an action was successful

#### Collapse

```text
<Collapse>

# Lorem ipsum

Etiam blandit diam sit amet pharetra pellentesque. Integer auctor nisl et sodales
imperdiet. Integer vitae tincidunt augue. Duis condimentum lectus at tincidunt
vehicula. Maecenas ultricies erat id nunc tempus, malesuada accumsan justo dignissim.
Nam interdum vitae arcu et pharetra. Integer eget faucibus arcu.

</Collapse>
```

**Show**

#### Snippets

**Internal Snippet**

Snippets from the local repository can be embedded on the site \(either inside a `<Collapse>` component or outside\) via the following syntax:

**WITHIN COLLAPSE**

```text
<Collapse>

`embed:internal/community/example-include.py`

</Collapse>
```

**Show**

**STANDALONE**

```text
`embed:internal/community/example-include.py`
```

```text
import asyncio
import os
from datetime import datetime

from lib import async_rpc_server


class Manager:
    """Manages shards.  assigns shard nodes their ids and checks if they are alive"""
    def __init__(self, total_shards):
        print(f"Number of shards: {total_shards}")
        self.total_shards = total_shards
        self.registered = 0
        self.last_checkin = {}
        self.store = {}

    async def handle_task(self, method, *args, **kwargs):
        return (await (getattr(self, method)(*args, **kwargs)), 200)

    async def register(self):
        """Returns the next shard id that needs to be filled as well as the total shards"""
        if self.registered >= self.total_shards:
            raise Exception("Shard trying to register even though we're full")
        self.registered += 1
        print(f'Shard requested id, assigning {self.registered}/{self.total_shards}...')
        self.store[self.registered - 1] = {'shard_id': self.registered - 1}
        return {'shard_id': self.registered - 1, 'shard_count': self.total_shards}
```

**External Snippet**

Snippets from online sources can be asynchronously loaded onto the page upon render. This means that they can be updated independently of the module build.

Without static syntax highlighting, extra steps must be taken to enable proper highlighting at runtime. This comes in the form of adding language imports to `/src/languages.js`. For example, to enable python, the following line must be added to `languages.js`:

```text
import "prismjs/components/prism-python.js";
```

**WITHIN COLLAPSE**

```text
<Collapse>
  <ExternalSnippet
    src={"https://gist.githubusercontent.com/jazevedo620/a28cdc92a624c290ccf91541b418bdae/"
       + "raw/1bfef7f4fb49df08d3685611354b71bd9424d4a6/app.py"}
    language="python"
  />
</Collapse>
```

**Show**

**STANDALONE**

```text
<ExternalSnippet
  src={"https://gist.githubusercontent.com/jazevedo620/a28cdc92a624c290ccf91541b418bdae/"
     + "raw/1bfef7f4fb49df08d3685611354b71bd9424d4a6/app.py"}
  language="python"
/>
```

```text
from aiohttp import web
import asyncio
import socketio
from functools import partial

from lib.config import which_shard
from lib.auth import JWT
from lib.async_rpc_client import shardRPC


sio = socketio.AsyncServer(async_mode='aiohttp')
app = web.Application()
sio.attach(app)

@sio.event
async def join(sid, message):
    guild_id = message['room']
    print("decoding jwt...")
    jwt = JWT(token=message['jwt'])
    print("checking membership...")
    resp, _ = await shard_client.call('is_member', jwt.id, guild_id, routing_key=f"shard_rpc_{which_shard(guild_id)}")
    print(resp)
    if resp['member']:
        sio.enter_room(sid, message['room'])
        await sio.emit('my_response', {'data': 'Entered room: ' + message['room']}, room=sid)
    else:
        await sio.emit('my_response', {'data': 'You don\'t have permission to enter: ' + 
```

