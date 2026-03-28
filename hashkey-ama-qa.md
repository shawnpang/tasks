# HashKey Chain Horizon Hackathon AMA — Shawn Pang (AllScale)

**Event:** HashKitchen Horizon Hackathon AMA #2
**Date:** March 26, 2026
**Host:** Ini (HashKey Chain)
**Speakers:** Victor (HashKey), Hui (TinyFish), Shawn Pang (AllScale), Alex (HashKey)

---

## Introduction

**Q: Can you introduce yourself and what you're building?**
**Answered by:** Shawn Pang (AllScale)

I'm Shawn, co-founder and CEO at AllScale. We're building a non-custodial neobank designed for unbanked businesses and AI agents.

If you're running a business from an emerging market, it can be really tricky to get a bank account in the US, Hong Kong, or Singapore. But with AllScale, you can get an account in seconds — just scan your face or fingerprint and sign up with a passkey. If you're an AI agent, you can get an account through CLI.

The best part is you also have the option to do additional KYC or KYB to unlock fiat features — an actual bank account, a crypto card, the whole suite. Essentially, we're building a non-custodial neobank that anyone can access permissionlessly on-chain, with a complete set of business solutions.

---

## Q1: What are the biggest challenges when allowing AI agents to interact directly with on-chain assets or execute transactions?
**Answered by:** Hui (TinyFish), Shawn Pang (AllScale)

I see two main challenges: **authorization** and **security**.

### Security

In the past two weeks, we saw two really interesting cases of similar attacks in both Web2 and Web3.

First, there was a whale who lost nearly $50 million in a single DEX transaction. They were using a router for a series of transactions on a DEX, and because they didn't account for potential slippage — combined with some systematic design problems — they clicked confirm without knowing what would happen. They lost more than $30 million in one transaction.

Second, we also saw a LiteLLM hack very recently — a classic supply chain attack. A lot of projects on GitHub, whether open source or privately owned, rely on LiteLLM. Even if you don't use the repo directly, you might be using another repo built on top of it. The hacker injected suspicious commands into the library, causing leakage of private info like security tokens and transaction history. It was only discovered because the hacker didn't do it properly and caused memory to overflow.

From this, we can see something really interesting. Both in DeFi and in open source development, we're seeing what I call **"Lego projects"** — you don't build everything from scratch. You're building on top of other people's projects, and there's a high chance one of those packages might be compromised. Security, especially supply chain security, is very important and often overlooked.

### Authorization

This is something AllScale deeply believes in. We were actually really early in exploring whether we could allow AI agents to do transactions for our clients. We launched test cases where an AI agent can own AllScale accounts, send out invoices, track payments, and follow up on unpaid invoices.

But we were intentionally slow on a full launch because building something for AI agents is actually easy — if you understand how it works, you could vibe-code something in a couple of hours. But making sure you optimize for **human-in-the-loop** and proper **authorization** is a completely different story.

Right now, most projects just give an agent a private key — many deploy on Vercel with the private key as a hidden environment variable. We definitely don't recommend that. Other approaches include custodial solutions with spending limits, or building human-in-the-loop experiences where the AI agent raises a transaction and a human confirms it. These are the main blockers we need to solve for mass adoption of AI agents doing on-chain transactions.

---

## Q2: What does mainstream payment adoption in Web3 actually require? What's the missing piece?
**Answered by:** Hui (TinyFish), Shawn Pang (AllScale)

Let's be really honest — we're still pretty early in terms of crypto payment adoption. A lot of the payment volume we see actually comes from on-chain trading, not real-world transactions. Even if we count all of those, it's still a very small fraction of total B2B payment volume.

**Three blockers:**

### 1. Compliance

We're seeing huge progress here — the Genius Act and upcoming Clarity Act help a lot, which is why traditional businesses are coming back into the space. But we're not there yet. In the past, businesses couldn't easily figure out how to handle tax, AML, or stay compliant while accepting crypto or stablecoin payments.

### 2. Not enough good solutions

It might seem overcrowded, but if we look honestly at something as basic as on/off ramps — we actually don't have that many solutions that are both compliant and have good UX.

### 3. UX

For so many years, we've counted on new technologies or features to attract users into crypto. But most people won't understand how crypto works, no matter how attractive it is. The UX is just really bad. We don't have a whole ecosystem ready yet.

**The key insight: if we want crypto mass adoption, we have to make crypto invisible.** This is what we believe in at AllScale. If you try our invoicing or checkout product, you don't even realize you're interacting with a blockchain. Everything is non-custodial — it's a completely new experience compared to MetaMask or TokenPocket. Once we address these three blockers, we still need to build the ecosystem.

---

## Q3: What would a breakout AI and payment project from this hackathon look like?
**Answered by:** Victor (HashKey), Hui (TinyFish), Shawn Pang (AllScale)

Two types of projects I'm personally really interested in:

### 1. Invisibility

Invisibility of both AI and crypto. You want to build something that works 100% and people just take for granted — users don't even realize it's on-chain or powered by AI.

In the past, if you built a service agency, investors didn't look twice. But now AI can complete entire workflows while keeping everything invisible — it's essentially "AI as a service" or even "service as a service."

Same with crypto. Our AllScale product feels like just another Airwallex or Monobank or PayPal. It works great. Except you can get an account in seconds — that's because everything is on-chain and non-custodial, so we don't have the friction of traditional payment products.

### 2. AI-native and crypto-native projects

Things that are really aggressive — projects that weren't even feasible before the recent advancement in crypto and AI. Things people wouldn't have even thought about.

---

## Q4: Will AI agents eventually become on-chain finance actors in payment networks? What needs to be solved first?
**Answered by:** Hui (TinyFish), Shawn Pang (AllScale), Alex (HashKey)

There's nothing inherently special about AI and crypto compared to AI and everything else — legal, marketing, coding, art, music. We're already seeing clearly how AI is changing everything.

But what's interesting is **AI coding**. A lot of innovation isn't driven by innovations in the vertical space first — it's driven by AI's ability to code. AI can learn to code, and then use coding skills to learn everything else.

**What's special about crypto is that it's designed really closely with coding.** On-chain transactions might seem tricky to a regular user, but they're incredibly intuitive from a coder's perspective. Traditional finance hides complexity — that's good for human users but bad for building on top of. Crypto, from day one, is open and transparent by default. Everything is designed really well for AI coding.

So the short answer is **yes** — we'll definitely see AI contributing to a lot of innovation here. It's because AI coding is improving so fast, and crypto is uniquely coder-friendly, making it easy for AI coding capabilities to expand into crypto.

---

## Q5: How can AI improve autonomous payments on-chain without compromising security?
**Answered by:** Shawn Pang (AllScale)

The answer is clear: we need to optimize for **human-in-the-loop** and **authorization**.

It's easy to give an AI agent a wallet. Everything is open source — you can literally replicate a whole project in hours. But if you want real adoption from sticky customers who don't complain, you need to optimize the experience around oversight.

That means:
- **Tracking:** Can the AI agent's owner easily track everything that's happening? Is there a clear dashboard? Is it intuitive?
- **Integration:** Can you integrate with tools like QuickBooks so owners can do tax reporting and stay compliant?
- **Authorization with guardrails:** For example, I want my AI agent to book my entire Southeast Asia trip — flights, hotels, everything — but keep the budget under $4,000. How do I make sure that actually happens?

Building experiences with human-in-the-loop and authorization is what we need if we actually want AI agent transactions on-chain to work.

---

*AllScale — Non-custodial neobank for unbanked businesses and AI agents. Get an account in seconds at allscale.io*
