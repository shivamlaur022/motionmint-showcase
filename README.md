<h1 align="center">MotionMint</h1>

<p align="center">
<b>Type one sentence. Get a narrated, animated explainer video.</b><br>
English, Hindi or Hinglish · vertical or landscape · built from scratch, first version in 2 days.
</p>

<p align="center">
<img src="https://img.shields.io/badge/Cloudflare_Workers-F38020?style=flat-square&logo=cloudflare&logoColor=white">
<img src="https://img.shields.io/badge/Hono-E36002?style=flat-square&logo=hono&logoColor=white">
<img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB">
<img src="https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white">
<img src="https://img.shields.io/badge/Azure_Speech-0078D4?style=flat-square&logo=microsoftazure&logoColor=white">
<img src="https://img.shields.io/badge/Azure_Container_Apps-0078D4?style=flat-square&logo=microsoftazure&logoColor=white">
<img src="https://img.shields.io/badge/Remotion-0B84F3?style=flat-square&logo=remotion&logoColor=white">
<img src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white">
<img src="https://img.shields.io/badge/Cloudflare_R2-F38020?style=flat-square&logo=cloudflare&logoColor=white">
</p>

<table align="center">
<tr><th>UPI PIN (Hindi)</th><th>QR codes (English)</th></tr>
<tr>
<td><img src="upi-pin-hindi.gif" width="240"></td>
<td><img src="qr-code-english.gif" width="240"></td>
</tr>
<tr>
<td align="center"><a href="upi-pin-hindi.mp4">▶ Watch with sound</a></td>
<td align="center"><a href="qr-code-english.mp4">▶ Watch with sound</a></td>
</tr>
</table>

> The source code is private. This repo explains what it does and how it works.

---

## 📊 At a glance

| | |
|---|---|
| **Input** | One sentence, a web link, or your own script |
| **Output** | MP4 with voice, captions, music, sound effects, plus an `.srt` file |
| **Languages** | English, Hindi, Hinglish |
| **Formats** | Vertical 9:16 (Reels, Shorts) or landscape 16:9 (YouTube) |
| **Length** | As long as needed (usually 1–2 min) or fixed 15, 30, 45 or 60 seconds |
| **Pipeline** | 11 stages, including fact checking and automatic quality review |
| **Cost to make** | About ₹70 for a 1.5 minute video |
| **Apps** | User studio (11 pages) and admin console (11 pages) |

---

## 🎬 From one line to a finished video

```mermaid
flowchart TB
    IN["✍️ Topic, link or script"] --> R1

    subgraph WRITE["Write"]
        R1[1 · Research<br/>web search, keep only facts<br/>found word-for-word on the page]
        R1 --> R2[2 · Script<br/>hook, simple example, ending]
        R2 --> R3{3 · Review<br/>user edits & approves}
    end

    subgraph MAKE["Make"]
        R3 --> R4[4 · Voice<br/>word-level timing]
        R4 --> R5[5 · Storyboard<br/>one moving world, nothing frozen > 2s]
        R5 --> R6[6 · Details<br/>numbers appear when spoken]
        R6 --> R7[7 · Assets<br/>icons, illustrations, logos]
        R7 --> R8[8 · Screenshots<br/>source pages with the quote highlighted]
        R8 --> R9[9 · Render<br/>music, voice levelling, MP4]
    end

    subgraph CHECK["Check"]
        R9 --> R10{10 · Quality check<br/>AI reviews a frame from every shot}
    end

    R10 -- pass --> OK[11 · ✅ Ready to download]
    R10 -- fail --> RF[↩️ Marked failed<br/>credits refunded automatically]
```

The UPI video explains payments through Ramu's chai stall: your phone, your bank, the network in between, and why your PIN stays safe. Objects stay on screen and move with the voice, so it feels like one animation instead of a slideshow.

---

## 🎛️ Video options

| Option | Choices |
|---|---|
| **Source** | Research it (web search, only facts it can link to) · From a link · My own script (40–6,000 characters) |
| **Language** | English · Hindi · Hinglish |
| **Length** | As long as needed · 15s · 30s · 45s · 60s |
| **Format** | Vertical 9:16 · Landscape 16:9 |
| **Tone** | Educational · Investigative · Calm · Hype · Funny |
| **Voice** | Female · Male |
| **Captions** | On or off · Highlight, Plain or Bold · Roman or Devanagari |
| **Extras** | Guide mascot · Sound effects · Skip script review |

Write the prompt naturally ("a 30 second Hindi reel on credit scores, funny tone") and the settings fill in by themselves.

---

## 🖥️ User studio (11 pages)

| Page | What you can do |
|---|---|
| **Landing** | How it works, sample videos, use cases, languages, pricing, FAQ |
| **Log in · Sign up · Forgot / reset password** | Account access |
| **Home** | Prompt box, example topics, scripts waiting for review, videos in progress, recent videos, credits |
| **Videos** | Library with search, language and format filters, bulk retry or delete |
| **New video** | Describe it, adjust settings, see credits left after |
| **Project** | Live progress, script editor per scene, sources with links, quality report, download MP4 and captions |
| **Credits & billing** | Credit packs via PayU, billing history, credit activity, automatic refunds |
| **Settings** | Profile, brand (end-card handle, accent colour, mascot), theme, shortcuts, password |

## 🛠️ Admin console (11 pages)

```mermaid
flowchart LR
    OV[📊 Overview<br/>revenue · spend · margin] --- OPS[⚙️ Operations<br/>videos · queue · failures]
    OV --- CU[👥 Customers<br/>users · payments · credits]
    OV --- IN[📈 Insights<br/>usage & costs]
    OV --- SY[🔧 System<br/>settings · audit log]
```

| Page | What it shows |
|---|---|
| **Overview** | Revenue, AI and compute spend, cost and margin per video, time to video, spend by stage |
| **Videos / Video detail** | Every video with cost by stage and model, pacing repairs, errors, files |
| **Queue & failures** | What's rendering now, failures in the last 24 hours, workers |
| **Users / User detail** | Credits, spend, margin, success rate; grant credits, suspend, change role |
| **Payments** | PayU orders and manual reconciliation |
| **Credits ledger** | Every credit movement with the balance after it |
| **Usage & costs** | Spend by provider and model, active users, most expensive videos |
| **Settings** | Sign-ups, maintenance mode, limits, credit packs and prices, cost alerts, video retention |
| **Audit log** | Every admin action, who did it and what changed |

---

## ⚙️ How it runs

```mermaid
flowchart TB
    U[🖥️ User studio] --> API[API<br/>Hono on Cloudflare Workers]
    A[🛠️ Admin console<br/>separate Worker] --> API
    API --> DB[(Supabase / PostgreSQL<br/>jobs · credits · users · ledger)]
    API -- starts when there's work --> J[🎬 Render jobs<br/>Azure Container Apps]
    J -- next job --> DB
    J --> AI[Claude · Azure Speech]
    J --> R2[(Cloudflare R2<br/>videos)]
    U -- signed link, 1 hour --> R2
    PU[💳 PayU] --> API
```

| | |
|---|---|
| **Pay only while rendering** | Render jobs start when there's work and shut down when there isn't. No fixed server bill. |
| **Queue in Postgres** | Workers take the next job with `FOR UPDATE SKIP LOCKED`, so two never take the same one |
| **Safe credits** | Balance can't go below zero; charges, refunds and purchases run only on the server, each once |
| **Auto refunds** | Failed videos give the credits back |
| **Expiring links** | Videos are shared through signed links that expire in an hour |

```mermaid
flowchart LR
    B[Buy pack<br/>PayU] --> C[(Credits)]
    C --> V[Start video<br/>credits held]
    V --> D{Finished?}
    D -- yes --> K[Credits spent]
    D -- no --> RF[Credits returned]
```

---

## 💭 What I learned

My first videos looked like slideshows, a new picture every few seconds. They only started to feel like real animation once the whole video became one scene where things stay and move with the voice.

---

<p align="center">
Shivam Kumar · <a href="mailto:proffesorrk@gmail.com">proffesorrk@gmail.com</a> · <a href="https://www.linkedin.com/in/shivam-kumar-28b40b306/">LinkedIn</a>
</p>
