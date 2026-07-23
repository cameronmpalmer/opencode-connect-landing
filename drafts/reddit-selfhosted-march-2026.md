# r/SelfHosted Post Draft — March 2026

| Field | Value |
|-------|-------|
| **Status** | ✅ Posted — March 9, 2026 |
| **URL** | https://www.reddit.com/r/selfhosted/comments/1rpaekr/im_building_a_native_android_client_for_opencode/ |
| **Prepared** | March 9, 2026 |
| **Flair** | Use "Self Promotion" if available, otherwise "Discussion" |
| **UTM link** | `https://cameronmpalmer.github.io/opencode-connect-landing/?utm_source=reddit&utm_medium=post&utm_campaign=launch&utm_content=selfhosted` |

---

## Post Title

```
I'm building a native Android client for OpenCode — tested every existing app first, they all fail over Tailscale
```

---

## Post Body

```
I run OpenCode on a home server and wanted to control it from my Pixel phone over Tailscale. It seemed like it should be simple. I discovered there are already three Android clients built for this, so I tested all of them. Every single one failed before I could send a message.

I'm Cameron, and I'm building an alternative -- but I want to share what I found first because it's relevant to anyone in this community trying to do the same thing.

Test setup:
OpenCode v1.2.22, accessible via Tailscale at a plain HTTP 100.x.x.x:4097 URL.
Health endpoint confirmed healthy. Stock OpenCode web UI fully working from the same Android device over the same Tailscale connection. Every failure below is client-side.

App 1: OpenCode Remote (giuliastro/opencode-remote-android)
Capacitor-wrapped React app -- not native Android. Required disabling Pixel security to sideload. Connected to the server successfully (the one bright spot), then displayed a blank white screen when starting a session. No error, no guidance. Dead end.

App 2: P4OC / Pocket for OpenCode (theblazehen/P4OC) — $0.99 on Play Store
Two failure modes depending on how you enter the URL:
No protocol prefix -> received HTML instead of JSON (URL parsing bug)
https:// prefix -> "Unable to parse TLS packet header" (Tailscale handles encryption; the server runs plain HTTP; the app doesn't handle this)
Never got past the connection screen.

App 3: OC Remote (crim50n/oc-remote)
The most polished-looking of the three -- Material 3, AMOLED dark mode, multi-server support, 15 locales, 16 releases of feature work. On first connect: "Server is not responding." No diagnostics, no suggestions. Can't get past the home screen.

The pattern: None of these apps handle HTTP-over-Tailscale correctly. None auto-detect HTTP vs HTTPS. None give useful error messages. The most common self-hosted OpenCode setup -- local server + Tailscale -- is completely unsupported by every existing client.

What I'm building: OpenCode Connect. Native Kotlin/Jetpack Compose, $4.99 one-time purchase, no subscription. Priority #1 is Tailscale/plain-HTTP connections that work on first try, with clear diagnostics when something's wrong. Everything else is secondary.

Waitlist: https://cameronmpalmer.github.io/opencode-connect-landing/?utm_source=reddit&utm_medium=post&utm_campaign=launch&utm_content=selfhosted

Happy to share more failure details or discuss what robust connection handling should look like. Has anyone gotten any of these apps working over Tailscale?
```

---

## Checklist Before Posting

- [ ] Verify correct flair is selected (Self Promotion > Discussion)
- [ ] Confirm UTM link is included and unmodified
- [ ] Re-read r/SelfHosted Rule 2: "If you post about your own work, say so clearly" ✓ (covered in paragraph 2)
- [ ] Optional: soften P4OC section if ongoing dialogue with theblazehen warrants it

---

## Draft Notes

- **Builder identity disclosed in paragraph 2** — not buried, not first sentence, but well before any findings. Compliant with r/SelfHosted Rule 2.
- **Tailscale angle is the lead value** — directly relevant to this community's use case.
- **No GLM-5/Kimi references** — removed; r/SelfHosted audience won't know these models.
- **Server version: v1.2.22** — correct version throughout.
- **Ends with a genuine question** — invites community engagement, reduces pure-promotion feel.
- **P4OC tone** — factual and neutral. theblazehen had a constructive exchange on r/LocalLLaMA before removal; no hostility warranted.
