<h1 align="center">MotionMint</h1>

<p align="center">
<b>Type one sentence. Get a narrated, animated explainer video.</b><br>
English, Hindi or Hinglish. First working version built in 2 days.
</p>

<p align="center">
<img src="https://img.shields.io/badge/Cloudflare_Workers-F38020?style=flat-square&logo=cloudflare&logoColor=white">
<img src="https://img.shields.io/badge/Hono-E36002?style=flat-square&logo=hono&logoColor=white">
<img src="https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white">
<img src="https://img.shields.io/badge/Azure_Speech-0078D4?style=flat-square&logo=microsoftazure&logoColor=white">
<img src="https://img.shields.io/badge/Remotion-0B84F3?style=flat-square&logo=remotion&logoColor=white">
<img src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white">
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white">
</p>

<table align="center">
<tr>
<th>UPI PIN (Hindi)</th>
<th>QR codes (English)</th>
</tr>
<tr>
<td><img src="media/upi-pin-hindi.gif" width="260"></td>
<td><img src="media/qr-code-english.gif" width="260"></td>
</tr>
<tr>
<td align="center"><a href="media/upi-pin-hindi.mp4">▶ Watch with sound</a></td>
<td align="center"><a href="media/qr-code-english.mp4">▶ Watch with sound</a></td>
</tr>
</table>

> The source code is private. This repo shows what it makes and how it works.

---

## ✨ From one line to a finished video

```mermaid
flowchart LR
    T["✍️ Topic<br/><i>What is a UPI PIN?</i>"] --> R[🔎 Research<br/>real sources]
    R --> S[📝 Script<br/>hook, example, ending]
    S --> V[🎙️ Voice<br/>EN · HI · Hinglish]
    V --> B[🎬 Scenes<br/>one moving world]
    B --> X[🖥️ Render<br/>1080×1920 + captions + music]
    X --> Q{✅ Quality check}
    Q -- pass --> U[📲 Video ready]
    Q -- fail --> F[↩️ Credits refunded]
```

The UPI video explains payments through Ramu's chai stall: your phone, your bank, the network in between, and why your PIN stays safe. The same objects stay on screen and move with the voice, so it feels like one animation instead of a slideshow.

---

## ⚙️ How it runs

```mermaid
flowchart TB
    U[User studio<br/>React] --> API[API<br/>Hono on Cloudflare Workers]
    ADM[Admin panel<br/>own Worker] --> API
    API --> DB[(Supabase / PostgreSQL<br/>jobs · credits · users)]
    API -- starts when there's work --> J[Render jobs<br/>Azure Container Apps]
    J -- pick next job --> DB
    J --> AI[Claude · Azure Speech]
    J --> R2[(Cloudflare R2<br/>finished videos)]
    U -- signed link, expires in 1h --> R2
```

| | |
|---|---|
| **Pay only while rendering** | Render jobs start when there's work and shut down when there isn't. No fixed server bill. About ₹70 per 1.5 minute video. |
| **Job queue in Postgres** | Workers grab the next job with `FOR UPDATE SKIP LOCKED`, so two workers never take the same one. |
| **Credits can't go wrong** | Balance can't drop below zero. Charges, refunds and purchases only run on the server, each with an idempotency key, so a payment is never counted twice. |
| **Auto refunds** | If a video fails, the credits come back on their own. |
| **Admin panel** | Usage, costs, users, payments and an activity log, as a separate app. |

```sql
-- Simplified idea, not the real code
select id from render_jobs
where status = 'queued'
order by created_at
for update skip locked
limit 1;
```

---

## 💭 What I learned

My first videos looked like slideshows, a new picture every few seconds. They only started to feel like real animation once the whole video became one scene where things stay and move with the voice.

---

<p align="center">
Shivam Laur · <a href="mailto:proffesorrk@gmail.com">proffesorrk@gmail.com</a> · <a href="https://www.linkedin.com/in/shivam-kumar-28b40b306/">LinkedIn</a>
</p>
