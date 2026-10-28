<p align="center">
  <img src="banner.svg" alt="Deck 83 retro cassette music player" width="100%">
</p>

<h1 align="center">Deck 83</h1>

<p align="center">
  A retro cassette-deck music player for your own songs.<br>
  Spinning reels, a purple spectrum meter, and accounts that work on any device.
</p>

<p align="center">
  <a href="https://stalwart-florentine-ee5f6c.netlify.app"><img src="https://img.shields.io/badge/Live%20site-open%20Deck%2083-b57bff?style=for-the-badge" alt="Live site"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML%20%2B%20CSS%20%2B%20JS-no%20build%20step-3a3d42?style=flat-square" alt="Plain HTML, CSS and JS">
  <img src="https://img.shields.io/badge/Accounts-Supabase-3ecf8e?style=flat-square" alt="Accounts by Supabase">
  <img src="https://img.shields.io/badge/Hosted%20on-Netlify-00c7b7?style=flat-square" alt="Hosted on Netlify">
</p>

---

## Try it

**https://stalwart-florentine-ee5f6c.netlify.app**

Create an account with your email, log in, and press Play.

## What it does

| | |
|---|---|
| 📼 **Tape deck look** | Spinning reels, a cassette label that shows the current track, and chunky hardware-style buttons. |
| 🎛️ **Live spectrum meter** | A purple LED meter that moves with the music. |
| 🎵 **Built-in tracks** | Three chiptune songs generated right in the browser, so there is something to play straight away. |
| ➕ **Your own songs** | Add audio files from your device, play them, and delete them with the ✕ button. |
| 👤 **Real accounts** | Sign up once and log in from any device. You stay logged in after closing the page. |
| ⌨️ **Keyboard controls** | Space plays or pauses. Left and right arrows change tracks. |

## How it works

```
index.html   Homepage with About, FAQ, and links to sign up or log in
player.html  Login card and the music player (same page)
config.js    Your Supabase URL and anon key
```

- **Accounts** are handled by [Supabase](https://supabase.com) (email and password).
- **Songs** you add are stored in your browser on the device where you add them. They are never uploaded, so they do not appear on your other devices.
- **Built-in tracks** are made with the Web Audio API.

## Set up your own copy

1. **Create a Supabase project** at supabase.com.
2. **Email sign-in:** under Authentication, then Sign In / Providers, then Email, turn off *Confirm email* if you want people to log in right after signing up.
3. **Copy your keys** from Project Settings, then API Keys: the Project URL and the `anon` public key.
4. **Edit `config.js`:**
   ```js
   window.DECK83_CONFIG = { url: "https://YOUR-PROJECT-ID.supabase.co", anonKey: "YOUR-ANON-KEY" };
   ```
5. **Deploy** `index.html`, `player.html`, and `config.js` together to Netlify (drag the folder onto app.netlify.com/drop).
6. **Set the Site URL** in Supabase, under Authentication, then URL Configuration, to your Netlify address.

> Never put a `service_role` or secret key in `config.js`. Only the `anon` key belongs there.

## Good to know

- Deck 83 plays built-in tracks and audio files from your device. It does not stream from Spotify or other services.
- Any audio your browser can play works, including MP3, WAV, M4A, and OGG.
- Clearing your browser data removes the songs you added on that browser. Your account stays.

## Ideas for later

- [ ] Songs that follow you across devices (Supabase Storage)
- [ ] Shuffle and repeat
- [ ] A progress bar you can drag
- [ ] A VU needle and a tape-flip animation
