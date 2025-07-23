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

## Need help? Ask Tico!

<div class="tico">
  <div class="tico-tico-message">
    <img src="https://placehold.co/400x400" />

    <div>Hi, I'm Tico! I can answer questions about Voiceflow and point you towards docs. How can I help?</div>
  </div>

  <div class="tico-user-message">
    <form id="tico-form">
      <input type="text" id="tico-message" />

      <img src="https://placehold.co/400x400" />
    </form>
  </div>
</div>

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

    <CardTile href="./agents" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYk32PRud4xvHiSLdUJE7T2askXuFCm1RcjpZWM" title="Memory" description="Reference previous messages" />

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

  <CardTile href="./custom-interfaces" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYktzB2dbcql98M6riPKymkZ4CSD0cowfj1JRGv" title="Voiceflow API" description="Build your own interface" />
</div>

<br />

## Improve your agent

### Insights

Understand how your agent is being used

<div class="home-grid">
  <CardTile href="./chat-widget" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkoxdT412fXpt4RuYNQ8VldT29GHDUiFMj7hA0" title="Transcripts" description="View past conversations" />

  <CardTile href="./telephony" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkde8At3Glpu1oeO8lNrvZq7mJiBcVy0XgAjEb" title="Analytics" description="Monitor usage and metrics" />

  <CardTile href="./custom-interfaces" icon="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkH2fnAMBeCj2fNFhVHQauMGS9vlA6qbZmTgP8" title="Evaluations" description="Measure agent success" />
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
  
/* Tico on home */
.tico img {
  width: 3em;
  border-radius: 50%;
  display: inline-block;

}
  
.tico-tico-message div {
    display: inline-block;
    margin-left: 1em;
    background-color: #53575B;
    padding: 1em;
    border-radius: 4px;
  }

  .tico-tico-message div:after {
    content: '';
    position: absolute;
    left: 0;
    top: 50%;
    width: 0;
    height: 0;
    border: 0.219em solid transparent;
    border-right-color: #53575B;
    border-left: 0;
    margin-top: -0.219em;
    margin-left: -0.219em;
}

.tico-user-message {
	margin-top: 1em;  
}

.tico-user-message input {
  margin-right: 1em;
  background-color: #ECF0F4;
  border-radius: 4px;
  width: calc(100% - 5.5em);
  padding: 0.7em;
  color: #202428;
  border: 1px solid #13171B;
}

</style>
`}</HTMLBlock>

\<script>
&#x20; document.getElementById('tico-form').addEventListener('submit', function(event) \{
&#x20;   event.preventDefault(); // Prevent form from actually submitting (page reload)
&#x20;  &#x20;
&#x20;   // You can add additional logic here, like validating or processing form data

&#x20;   // Open Voiceflow chat
&#x20;   if (window\.voiceflow && window\.voiceflow\.chat) \{
&#x20;     window\.voiceflow\.chat.open();
&#x20;   } else \{
&#x20;     console.warn('Voiceflow chat is not loaded');
&#x20;   }
&#x20; });
\</script>