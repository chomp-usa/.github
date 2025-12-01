# .github
# 🍽️ Chomp – Short-Form Food Discovery

Welcome to the **Chomp** GitHub organization.

Chomp is a mobile-first, TikTok-style app that helps you decide *where to eat* using short, hyper-local food reels. Open the app, start swiping, and instantly see what’s good around you.

---

## 🌟 What Chomp Does (User Experience)

### Open the app → instant food feed  
You land in a **vertical reel feed** of nearby restaurants. Each reel is a quick video showing a dish, the vibe, price range, and distance from you. Swipe up/down to keep browsing like TikTok/Reels.

### Tap into details or the map  
On any reel you can:

- See basics: rating, price, tags like “late night”, “vegan-friendly”.
- Tap **“Take me there”** to open directions in Google/Apple Maps.
- Jump to the **Map tab** to see all nearby spots as pins, then watch reels for a specific place.

### See what friends are doing  
In the **Social tab**, you see where friends have eaten, their reels, and recent visits around you. It turns “where should we eat?” into a social, visual experience.

### Upload your own reels  
In the **Post tab**, you can record or upload a short video of your meal, tag the restaurant, add a caption, and share it to the feed so others can discover it.

### Tune your recommendations  
In **Profile**, you can set:

- Budget / price range  
- Dietary needs (vegetarian, vegan, halal, etc.)  
- Allergies  
- Favorite cuisines  

Chomp uses this, plus your location and activity, to push more relevant reels to the top of your feed.

---

## 🎥 Where the content comes from

Chomp’s reels come from **three main sources**, so there’s always something to watch:

1. **Real people on Chomp (user-generated content)**  
   Users record quick videos of their meals directly in the app. We upload, process, and stream those clips so you can instantly share and browse authentic, on-the-ground food content.

2. **Curated reels from existing platforms**  
   We tap into public food videos from places like TikTok, Instagram, and YouTube (using their official APIs). When a reel is clearly about a specific restaurant, we link it into Chomp so you can discover those spots in the same swipe-able feed — **without re-hosting the video**.

3. **AI-powered “cold start” previews**  
   For great restaurants that don’t yet have user videos, we generate short preview reels using generative video and voice tools. These clips give you a quick sense of the vibe, menu, and location until real users start posting their own content.

---

## 🧱 High-Level Architecture (Planned)

While this org will evolve, the high-level vision looks like this:

- **Mobile App (MVP built)**
  - Expo + React Native + TypeScript
  - Bottom tabs: Feed, Map, Post, Social, Profile
  - Currently wired to realistic **mock data** for proof-of-concept

- **Backend (planned)**
  - Node.js + TypeScript services (Feed, Places, User/Social, Upload & Media, Realtime)
  - Postgres as system of record (restaurants, videos, users, visits, comments)
  - Redis for feed caching, hot counters (likes/views), sessions, rate limiting
  - Search/geo index for “nearby” and full-text search
  - Realtime layer for likes/comments
  - Media pipeline via a streaming provider (Mux / Cloudflare Stream / AWS IVS)
  - Generative content pipeline (OpenAI Sora, Google video model, ElevenLabs, etc.)

---

## 📁 Repositories in This Organization

(Names may change as the project grows.)

- **`chomp-mobile`**  
  Expo + React Native mobile client. Frontend MVP with:
  - Feed UI and reel viewer
  - Map view with restaurant pins
  - Social/Profile stubs
  - Mock data simulating future backend responses

- **(Future) `chomp-backend`**  
  Node.js/TypeScript backend services, APIs, and integrations (media, auth, gen-AI, POI, maps).

- **(Future) `chomp-infra`**  
  Infrastructure-as-code (IaC), deployment, CI/CD, observability.

---

## 🚀 Current Status

- ✅ Frontend MVP scaffolded with mock data (app shell, tabs, basic Feed/Map/Reel viewer flows).
- 🛠️ Next steps:
  - Wire real backend APIs
  - Integrate media streaming provider for real video playback
  - Add realtime likes/comments
  - Launch generative cold-start pipeline for restaurants with no content

---

## 🤝 Contributing / Collaboration

Right now Chomp is in an early, fast-moving phase. If you’re collaborating on this:

- Use feature branches and pull requests.
- Keep README and architecture docs up to date as things evolve.
- Prefer small, well-scoped changes over giant PRs.

(If you’re an external visitor: feel free to explore the repos — feedback and ideas are always welcome.)

---

## 📬 Contact

Questions, ideas, or want to collaborate?

- Open an issue in the relevant repo  
- Or reach out to the maintainer directly via the contact info in their profile

Thanks for checking out **Chomp** 🐊🍝 — where “Where should we eat?” becomes “Oh, that place looks fire, let’s go.”
