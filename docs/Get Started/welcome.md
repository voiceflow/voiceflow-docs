---
title: Welcome to Voiceflow's docs
excerpt: >-
  Build, manage, and deliver chat and voice agents for customer support and
  beyond.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---
<Columns layout="auto">
  <Column>
    <FeaturedCard header="Getting Started with Custom Components" />
  </Column>

  <Column>
    <FeaturedCard header="Getting Started with Custom Components" />
  </Column>
</Columns>

<br />

## Build an AI agent

<div class="home-grid">
  <div>
    ### Steps

    The building blocks of your agent

    <CardTile href="./agents" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkOgU65Dd5Aj1RBWVpvSMPindJHe8u0YCkLQso" title="Agent step" description="Have conversations with users" />

    <CardTile href="./prompt-step" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkQDb5qhu5eBZtroaHsTPyX3FngQuxIODK9ESU" title="Prompt step" description="Generate a single response using AI" />

    <CardTile href="./custom-actions" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkZ1WABJXkb1uUDkwRvF9HmdJsTyAnWQC0XgMo" title="Custom action step" description="Hook into advanced capabilties" />
  </div>

  <div>
    ### Capabilities

    Upgrade your agent's abilities

    <CardTile href="./agents" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkjDAU0PnIfFXj0DI1tHlCbnWGqRwsmUyZe4p2" title="Knowledge base" description="Add knowledge to your agent" />

    <CardTile href="./agents" icon="fa-brain" title="Memory" description="Reference previous messages" />

    <CardTile href="./variables" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkobm1MHV2fXpt4RuYNQ8VldT29GHDUiFMj7hA" title="Variables" description="Store values during conversations" />
  </div>

  <div>
    ### Tools

    Deeply integrate with your business

    <CardTile href="./tools" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkxyenLYlHB63EAecr4ldMRpWtKsU5fLaQgvGk" title="Integrations" description="One click integrations" />

    <CardTile href="./function-step" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYk4Nq10b5rotc4F1GyVLOWXpsqzuk68RiKw2eB" title="Functions" description="Run code inside your agent" />

    <CardTile href="./api-step" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkIUuDUXNn8fDhcCkQMZtqgsamUN1PR6HTVjX0" title="APIs" description="Connect to any service" />
  </div>
</div>

<br />

## Deploy your agent

### Interfaces

Choose how users interact with your agent

<div class="home-grid">
  <CardTile href="./chat-widget" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkhCBV3z6o2d3mou6ACgpXz8MelqjJTVRf9vDh" title="Web chat" description="Add your agent to your website" />

  <CardTile href="./telephony" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYk5E1ZDSzMKCWVSIegrm60uA8OXNGnvF3Zysxp" title="Phone" description="Accept inbound and outbound calls" />

  <CardTile href="./custom-interfaces" icon="fa-code" title="API" description="Build your own interface" />
</div>

<br />

## Improve your agent

### Insights

Understand how your agent is being used

<div class="home-grid">
  <CardTile href="./chat-widget" icon="fa-comments" title="Transcripts" description="Embed your agent onto your website" />

  <CardTile href="./telephony" icon="fa-phone" title="Analytics" description="Accept inbound and outbound calls" />

  <CardTile href="./custom-interfaces" icon="fa-code" title="Evaluations" description="Build your own interface" />
</div>

<br />

## Developer tools

<br />

<HTMLBlock>{`
<style>
  /*.content-toc { display: none !important; }
  .content-body { width: 100% !important; }*/
  .rm-Markdown h2 { margin-top: 0; }
  .rm-Markdown h3 { border-bottom: 0; padding-bottom: 0; margin-top: 0; margin-bottom: 0.3em !important; }
  .rm-Guides .content-body { max-width: 100%; }

   .home-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1rem;
  }

  @media (min-width: 1024px) {
    .home-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }

/* Home - featured cards */
  .featured-card {
    border: 1px solid #1C3BC8;
    padding: 2em 1em;
    border-radius: 4px;
    width: 100%;
    background: url("https://i.imgur.com/Lzj96mw.png"), #2b55ea;
    background-position: right;
    background-size: 15em;
    background-repeat: no-repeat;
  }

  .featured-card > span:first-child {
    display: block;
    font-weight: 600;
    font-size: 1.05em;
  }
</style>
`}</HTMLBlock>