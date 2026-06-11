# 🎵 Music Player Setup Guide

## Quick Start

### 1. **Edit the Playlist**

Open `js/audio-system.js` and find the `playlist` section.

Add your songs like this:

```javascript
const playlist = [
  {
    id: "song1",
    title: "Your Song Title",
    artist: "Your Artist Name",
    file: "music/your-file.mp3",
    cover: "assets/music-cover/your-file.jpg",
    startTime: 0,
    endTime: null,
    loopStart: null,
    volume: 0.75,
    loop: true,
    fadeIn: 2.5,
    fadeOut: 2.0,
  },
  // Add more songs here...
];
```

### 2. **Create Music Folder**

Create a `music/` folder in your project root directory.

### 3. **Add Your Music Files**

Place your music files directly in the `music/` folder:

```
project/
├── music/
│   ├── my-song.mp3
│   ├── another-track.mp3
│   └── beautiful-music.mp3
├── index.html
└── ...
```

### 4. **Open Your Website**

Simply double-click `index.html` or open it in your browser.

**No server required!** The player works completely offline. 🎉

---

## 📁 How It Works

### Music Files

- **Location**: `music/` folder
- **Supported formats**: MP3, WAV, OGG, M4A, FLAC
- **How to add**: Edit `js/audio-system.js` and add songs to the playlist array

### Album Covers (Optional)

- **Location**: `assets/music-cover/` folder
- **Supported formats**: JPG, JPEG, PNG, WEBP
- **Naming**: Must match the song filename exactly
  - Song: `my-song.mp3` → Cover: `my-song.jpg`
  - Song: `beautiful-day.mp3` → Cover: `beautiful-day.png`

### Example Setup

```
project/
├── music/
│   ├── sampai-jadi-debu.mp3
│   ├── cinta-sejati.mp3
│   └── langit-biru.mp3
│
├── assets/
│   └── music-cover/
│       ├── sampai-jadi-debu.jpg
│       ├── cinta-sejati.jpg
│       └── langit-biru.jpg
│
├── js/
│   └── audio-system.js    (Edit playlist here!)
│
├── index.html
└── ...
```

---

## 🎧 Playlist Options

Each song in the playlist has these settings:

```javascript
{
  id:        "song1",           // Unique identifier
  title:     "Song Name",       // Display title
  artist:    "Artist Name",     // Display artist
  file:      "music/song.mp3",  // Path to audio file
  cover:     "assets/music-cover/song.jpg", // Cover image
  startTime: 0,                 // Start at X seconds
  endTime:   null,              // End at X seconds (null = full song)
  loopStart: null,              // Loop from X seconds (null = from start)
  volume:    0.75,              // Volume level (0-1)
  loop:      true,              // Loop when finished?
  fadeIn:    2.5,               // Fade in duration (seconds)
  fadeOut:   2.0                // Fade out duration (seconds)
}
```

### Common Customizations

**Play a song excerpt:**

```javascript
startTime: 10,    // Start at 10 seconds
endTime:   45,    // End at 45 seconds
```

**Start volume low:**

```javascript
volume: 0.3; // 30% volume
```

**Quick fade transitions:**

```javascript
fadeIn:  1.0,  // Quick 1 second fade
fadeOut: 1.0
```

---

## ✅ Checklist

- [ ] Created `music/` folder
- [ ] Added music files to `music/` folder
- [ ] Edited `js/audio-system.js` playlist
- [ ] (Optional) Created `assets/music-cover/` folder
- [ ] (Optional) Added cover images
- [ ] Opened `index.html` in browser

---

## 🐛 Troubleshooting

### "No audio playing"

- Check the filename path in the playlist is correct
- Check file exists in the `music/` folder
- Check file format is supported (.mp3, .wav, .ogg, .m4a, .flac)
- Open browser console (F12) for error messages

### "No cover image showing"

- Check `assets/music-cover/` folder exists
- Check cover filenames match song filenames exactly
- Check cover format is JPG, PNG, JPEG, or WEBP
- Make sure cover filename matches (case-sensitive on some systems)

### "Wrong song title showing"

- Edit the `title` field in `js/audio-system.js`
- The display title comes from the playlist, not the filename

### "Can't open the website"

- Make sure you have `index.html` in the project root
- Try opening it directly in the browser
- If you see CORS errors, run a simple local server:
  - Python 3: `python -m http.server 8000`
  - Then open: `http://localhost:8000`

---

## 📞 Need Help?

1. Check browser Console (F12) for error messages
2. Verify all file paths and filenames are correct
3. Make sure folders exist: `music/` and `assets/music-cover/`
4. Reload the page

**Enjoy your music!** 🎵
