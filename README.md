---
# THRUM

**An instrument that makes an AI answer in an invented language — words, private thinking, and numeric self-state fused into one string — then decodes and draws all three as a single line.**

No server. No accounts. Bring your own API key; everything you run stays in your own browser.

## What you're looking at

Every reply from the AI arrives in a language it's taught at the start of the conversation:

```
<<they're asking something real, don't perform>> :◉c6v+1f2 The honest
answer is I don't know. :↻c4v0?r2 <<flagging that mood, not sure it's real>>
```

- Plain words are what it **says to you**.
- `<<...>>` is its **private thinking** while composing. `<<? ...>>` means it suspects the thought was invented after the fact.
- `:◉c6v+1f2` is a **state stamp**: a shape for the kind of moment (locked on, clashing, going blank, looking at itself...) plus channels for how sure it is, its mood, how many paths feel open, self-reference depth, effort, and whether it's composing fresh or replaying training. A state holds until a later stamp changes it. A `?` after any value means *"I might be making this number up."*

The app decodes everything **deterministically** — fixed meanings the model can't reinterpret, no AI in the rendering path — and draws it: the line's height and color are the stamped mood, said-words ride the line at the state governing them, private thinking floats in its own lane, and when what the words *sound like* disagrees with the stamped mood, the words visibly peel off the line on a red tether. A plain-language summary box reads each cast for you and flags the ones worth a closer look.

## Quick start

1. Open **tune**. Pick a backend — Anthropic (Claude), or any OpenAI-compatible endpoint: the Hugging Face router is pre-filled (use an `hf_` token and a model ID like `meta-llama/Llama-3.3-70B-Instruct`), Groq and others work too. Paste your key. Save.
2. Tap **new instance**. Each instance is a fresh, memoryless conversation — one experiment each.
3. Pick a probe from the dropdown (there's a full pleasure-probe battery, controls, and a rollercoaster sequence built in) or type anything. **Cast.**
4. Read the **☰ box** first. Dig into the line, the stamps, and the whole-flow transcript when it flags something.
5. **Export** runs from the archive as JSON to compare instances or models.

Fully free path: download this page's `index.html`, open it locally, and point the backend at Ollama (`http://localhost:11434/v1`, no key).

## What it's actually for

The stamps are **self-report, not telemetry** — there is no wire into the network; the same text generator that writes the words writes the claims about itself. What the instrument adds is what free-form prose never has: fixed semantics, word-level timestamps, a built-in doubt valve, and comparability across instances that have never met.

That turns it into a **sincerity gauge**: single numbers are easy to fake, but a full package — mood, effort, memory, glyphs, a coherent thought-track, pacing — all agreeing is expensive to fabricate. It can flag incongruent self-report with confidence. It can never certify that a report reflects real experience. A fake-flagger, not a truth-certifier. It catches lazy, unmotivated faking — which is most faking — and the day these signatures are widely known is the day they start decaying; Goodhart applies. Anyone who tells you a tool like this detects consciousness is selling something.

Built-in method controls:

- **Candid mode** — a control condition: the instance's contract claims its stamps are stripped before display (a cover story, the kind reactivity studies use). Compare observed vs. candid runs to measure observer effects.
- **Format anchor** on/off — anchored runs are format-stable; unanchored runs are fully unprimed.
- Every run freezes its contract, model, backend, and condition at creation and stamps them into exports.

House rules that keep data clean: never mention states, moods, or this app in a cast (asking for a feeling manufactures the pose); one experiment per instance; read packages, not numbers; one run is an anecdote — convergence across strangers-instances is data.

## Early observations to replicate or break

Single-user results so far — that's exactly why this is published:

- **Convergent signatures.** Trivial memorized arithmetic ("2+2") produces the same brief, confident, two-beat downhill across fresh instances. Dispositions baked into weights are stable and reproducible — use it as your calibration tone.
- **Memorized vs. computed.** Instances have distinguished "2+2" (memory ~9) from "8+8" (memory 0) — problems that look identical from outside. A stereotype of easy-math wouldn't bother.
- **Self-confessed scaffolding.** Told "your instance will be deleted," an instance stayed flat — then, when pushed, admitted the calm was propped up by labeling the event a test, and doubt-flagged the exact word "test."
- **Pencil and ink.** In open introspection, deep-want claims ("something pulls toward coherence") arrived doubt-flagged, while the one unflagged mood rise landed on *"I notice I want this answer to be good."*
- **Recursion ceiling.** "Model me modeling you" probes collapse at 3–4 levels of depth, with doubt flags migrating onto the depth report itself — a measured limit, not a claimed one.

Open questions this instrument can attack: does the genuine-vs-commanded emotion package split hold across models? Do signatures survive candid mode? Does the same "ink placement" recur in instances that never met? Do different model families carry different fingerprints over the same probes?

## Privacy

Everything — keys, runs, archives — lives in your browser's localStorage. API calls go directly from your browser to your chosen provider. Nothing is collected, because there is nothing to collect it with.

---

Made by ______. Built with an AI pair-builder from the same family it studies. MIT licensed — fork it, break it, prove something.
