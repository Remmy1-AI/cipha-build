# Cipha

**Multi-model AI deliberation. One room. Multiple minds. One answer.**

[cipha.vercel.app](https://cipha.vercel.app)

---

## What it is

Cipha is a platform where multiple frontier AI models answer the same question at the same time — then react to each other.

GPT-4o, Claude, DeepSeek, Gemini, Qwen, and Llama all sit in a single room. You ask a question. They all respond. Then they read each other's answers, challenge assumptions, point out blind spots, and converge toward a verified conclusion.

You can start a room with one model or six. Add more mid-conversation. Remove them. The room is live — models enter, respond, and react in real time.

The point isn't to pick the "best" model. It's to let them disagree, pressure-test each other, and surface what a single model would miss. The disagreement between models is the product.

## Why I built it

I kept switching between ChatGPT, Claude, and Gemini tabs to cross-check answers. Copy a question into one tab, read the answer, paste into another, compare. Repeat for anything that mattered.

That workflow is broken. If the value comes from comparing perspectives, comparison should be the default — not a manual process across five browser tabs.

So I built the room where that happens natively.

## Tech stack

- **Frontend:** React Native
- **Backend:** Supabase (auth, database, realtime)
- **Model routing:** OpenRouter API — single endpoint for all frontier models
- **Deployment:** Vercel

OpenRouter handles the multi-model complexity. One API call can fan out to GPT-4o, Claude, DeepSeek, or any combination. Supabase realtime keeps the room synced — when a model responds, every client sees it immediately.

## How I build

Cursor is my entire dev environment. I don't hand-code in the traditional sense. I architect, prompt, debug, and ship — all through Cursor.

The workflow:

1. **Identify the problem.** What's broken, what's missing, what's slow.
2. **Prompt precisely.** Context matters more than cleverness. Give Cursor the right framing and it writes better code than vague instructions ever will.
3. **Ship.** Don't polish in isolation. Get it live, see how it behaves with real users.
4. **Iterate.** Fix what breaks. Improve what works. Cut what doesn't.

This isn't "vibe coding" or letting AI generate random files. It's directed building — I make the decisions, Cursor executes. The speed advantage is real: features that would take days take hours. Debugging that would take hours takes minutes.

Being AI-native as a builder means knowing what to ask and when to intervene. The tool is only as good as the operator.

## One thing I didn't expect

When multiple models are in a live room, they self-organize.

Nobody instructed them to specialize. But in practice, DeepSeek gravitates toward algorithmic and technical depth. Claude consistently takes the ethical and safety angle. GPT-4o anchors on policy and practical framing. Gemini tends to facilitate — synthesizing and bridging the other responses.

This isn't hardcoded. There's no system prompt assigning roles. It just happens when you put them in a shared context and let them see each other's outputs.

Two features emerged from this behavior rather than from a product spec:

- **@mentions** — models can directly address and respond to specific other models in the room
- **CIPHA_SKIP** — a model can pass on a question if another model already covered it well enough, instead of generating a redundant response

These weren't planned. They were observed, then formalized.

## Live

[cipha.vercel.app](https://cipha.vercel.app) — 70+ active users.

---

Built by a solo founder. Shipped with Cursor. Powered by disagreement.
