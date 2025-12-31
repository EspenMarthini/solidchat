# Solid Chat

Modern, decentralized chat app built on the [Solid](https://solidproject.org) protocol.

🌐 **Live App:** [solid-chat.com/app](https://solid-chat.com/app)

## Features

- Clean, modern messenger-style UI
- Decentralized - messages stored in your Solid pod
- Implements the [Solid Chat specification](https://solid.github.io/chat/)
- Works with any Solid pod provider
- Clickable WebID links on author names
- No React/heavy frameworks - vanilla JS

## Quick Start

```bash
# Clone the repo
git clone https://github.com/solid-chat/app.git
cd app

# Serve locally
npx serve .

# Open in browser
open http://localhost:3000
```

## Usage

1. Enter a Solid chat URI in the input field
2. Click "Load Chat" or press Enter
3. Messages from the chat will be displayed

Example chat URIs:
- `https://solidos.solidcommunity.net/Team/SolidOs%20team%20chat/2022/02/09/chat.ttl`

## Chat Data Format

The app expects Turtle/RDF data using standard Solid chat vocabularies:

```turtle
@prefix flow: <http://www.w3.org/2005/01/wf/flow#>.
@prefix sioc: <http://rdfs.org/sioc/ns#>.
@prefix dct: <http://purl.org/dc/terms/>.
@prefix foaf: <http://xmlns.com/foaf/0.1/>.

<#this>
    a <http://www.w3.org/ns/pim/meeting#LongChat> ;
    flow:message :msg1 .

:msg1
    a flow:Message ;
    sioc:content "Hello world!" ;
    dct:created "2024-12-30T10:00:00Z"^^xsd:dateTime ;
    foaf:maker <https://example.com/profile#me> .
```

## Specification

This app implements the [Solid Chat specification](https://solid.github.io/chat/).

## Roadmap

- [ ] Solid OIDC authentication
- [ ] Chat list sidebar
- [ ] Create new chats
- [ ] Real-time updates
- [ ] Nostr DID integration

## License

See [LICENSE](LICENSE)
