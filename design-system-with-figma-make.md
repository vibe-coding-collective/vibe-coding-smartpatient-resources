# Keeping Figma Make on your design system

A practical guide to getting Figma Make to build things that actually look like MyTherapy, instead of a generic app you then fight to make on-brand.

---

## How far this guide goes

Everything below is what **one person can do inside Figma Make on their own**, and it will get you most of the way. The last mile (packaging your real MyTherapy component library so Make builds *from* it, wiring a token pipeline, and keeping design and code in sync as both change) is genuinely fiddly and is a project in itself.

---

## The problem, in your own words

From the pre-session survey and the discovery call:

- *"Figma Make alters the very specific screens that I share. It does not help with testing smaller tweaks with a set design system."*
- *"Prototyping something that looks like your app, with all the functionalities and the style and the visuals, is tricky. You can spend so much time trying to perfect a few things and it just doesn't happen, and credits are lost."*
- The **80% wall**: a nice-looking draft arrives fast, then the last on-brand mile won't come.

None of this means you are using it wrong. **Make drifts by default.** The fix is to change what it can *see* and what it can *reuse*.

## The one mental model

Make can only follow two things:

1. **The context you hand it** in the prompt.
2. **The parts of your design system that are named and published for reuse.**

Everything else, it invents. So there are exactly two levers, and this guide works through them cheapest-first.

---

## Step 1, Attach your context (5 minutes, do this today)

The fastest win, and the one most people miss: "**Make Attachments".** Instead of *describing* your app in a long prompt, drag the real material straight into the prompt box and tell Make to use it. Make reads attachments directly rather than approximating.

Attach any of:

- A **screenshot of the exact screen and state** you want it to match (not "our app" in general — the actual target).
- Your **brand / design guidelines** as a PDF.
- **Real (synthetic) data** as CSV or JSON, so the layout is built around true field names and lengths, not invented ones. (Use fake data — see [safety](./README.md#safety--security-in-your-world).)
- Reference **copy** so it uses your real microcopy and tone.

**Prompt shape:**

> Build this screen to match the attached screenshot exactly. Same layout, spacing, type scale and colours. Use the attached brand guidelines for anything not visible in the screenshot. Populate it with the attached data. Do not invent a new visual style.

This alone moves you from "generic app" to "recognisably ours" without touching your Figma libraries.

## Step 2, Name things for reuse, then publish (the biggest lever)

Make can only reference a design system that is **published as a library**, and it follows **use-based names**, not appearance-based ones. A token called `blue-500` tells the AI nothing about *when* to use it. `color/brand/primary` does.

Rename your tokens and components semantically:


| ❌ Make has to guess | ✅ Make follows              |
| ------------------- | --------------------------- |
| `blue-500`          | `color/brand/primary`       |
| `grey-100`          | `color/surface/subtle`      |
| `spacing-16`        | `spacing/component/padding` |
| `radius-8`          | `radius/card`               |
| `font-14`           | `typography/body/default`   |
| `Frame 42 copy`     | `Card/Product/Default`      |
| `Group 7`           | `PriceLabel`                |


Then:

- **Publish the library** (Make can only see published, up-to-date libraries) and **select it in the prompt box** so Make references your components, styles and variables directly.
- Organise variables into named collections (`color`, `spacing`, `typography`) using `/` separators, so Make can navigate them.
- Tip: Figma's **"Rename layers"** AI feature can bulk-fix default layer names from content and position.

Once your system is tokenised and published, "use our design system" stops being a hope and becomes something Make can actually resolve.

## Step 3, Make your components legible to the AI

Same library, very different results depending on how it is documented:

- **Write descriptions on components, styles and variables** — what it is *for*, when to use it, how it differs from a similar one. Agents read the **description field** explicitly; they do **not** reliably read a documentation frame you drew on the canvas.
- **Build a few higher-order components** — a whole `Card/Product` (image + title + price + button, with spacing baked in) beats making Make assemble loose atoms every time. It stacks your spacing and hierarchy decisions into one reusable block.
- **Define variants and properties** (size: small/medium/large, type: primary/secondary, state: default/disabled). Properties are one of the strongest signals you can give the agent.
- **Add an Examples page** — a handful of realistic, full compositions built from your system. Make can reference these as "this is what good looks like."

## Step 4 — A light-touch `Guidelines.md`

Every Make project has a `Guidelines.md` file (open **Code → the guidelines folder**). It is read on every future build, so a few hard rules there travel with the project. Keep it short and imperative:

```markdown
# MyTherapy Make guidelines

## MUST
- ALWAYS use components and tokens from the [MyTherapy] library. Never raw HTML elements or hardcoded hex values.
- If a needed component or token does not exist, STOP and ask me. Do not invent one.
- Match the attached screenshot's layout and spacing before adding anything new.

## Style
- Neutral surfaces by default; brand colour used sparingly for primary actions only.
- One primary button per view.
```

You *can* split this into many small files (`foundations/color.md`, `components/button.md`, decision trees for "which background token?"). That fuller multi-file structure is powerful but is where it starts becoming a real information-architecture job — which is training territory, not a first-afternoon task.

---

### Sources

- [Figma — Add guidelines to Figma Make](https://help.figma.com/hc/en-us/articles/33665861260823-Add-guidelines-to-Figma-Make)
- [Figma — Best practices to help Figma AI understand your design system](https://help.figma.com/hc/en-us/articles/38978644498199-Best-practices-to-help-Figma-AI-understand-your-design-system)
- [Figma — Write design system guidelines for Make kits](https://developers.figma.com/docs/code/write-design-system-guidelines/)
- [Figma blog — Build with more context and control (Make Kits & Attachments)](https://www.figma.com/blog/introducing-make-kits-and-make-attachments/)
- [Luke Finch — How to get your design system into Figma Make](https://finchy.medium.com/how-to-get-your-design-system-into-figma-make-3ac735205e7f)

