# 🕒 Twine SugarCube 2 – Live Clock

A lightweight, real-time date and time widget for [Twine](https://twinery.org/) games using the SugarCube 2 story format.  
Displays a live, updating clock directly within your passage or globally via `StoryCaption`.

## ✨ Features

- Live updating every second  
- AM/PM format with full date  
- Easy to integrate in any Twine passage  
- Optional fixed display in the UI (using `StoryCaption`)

## 📦 Installation

1. Copy the code from [`live-clock-sugarcube.html`](./live-clock-sugarcube.html).  
2. Paste it directly into a passage in your Twine project.  
3. (Optional) Paste it in the **StoryCaption** to make it appear on all pages.

```html
<span id="live-time"></span>
<script>
  const updateTime = () => {
    const d = new Date(),
      h = (d.getHours() % 12) || 12,
      m = d.getMinutes().toString().padStart(2, "0"),
      s = d.getSeconds().toString().padStart(2, "0"),
      ampm = d.getHours() < 12 ? "AM" : "PM",
      date = d.toDateString();

    document.getElementById("live-time").textContent =
      `${date} • ${h}:${m}:${s} ${ampm}`;
  };

  updateTime();
  setInterval(updateTime, 1000);
</script>
