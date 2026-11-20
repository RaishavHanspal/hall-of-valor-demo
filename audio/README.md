# Audio (drop-in)

`manifest.json` maps sound events to licensed audio files. Events not listed play the synthesized
placeholder from `src/audio/synth.ts`, so you can replace sounds one at a time.

```json
{
  "version": 1,
  "sprites": [
    {
      "src": ["sfx.webm", "sfx.mp3"],
      "map": {
        "reel_stop": [0, 220],
        "symbol_land": [300, 80],
        "anticipation_loop": [500, 2000, true]
      }
    }
  ],
  "music": {
    "music_base": { "src": ["music_base.webm", "music_base.mp3"] },
    "music_fs": { "src": ["music_fs.webm", "music_fs.mp3"] }
  }
}
```

- `map` values are `[startMs, durationMs]`, plus `true` for loops (anticipation, count-up).
- `src` lists formats in order of preference; the first one the browser can play is used.
- Events: spin_start, reel_stop, symbol_land, scatter_land, anticipation_loop, ways_update, way_win,
  lightning_burst, cascade_drop, multiplier_up, fs_trigger, fs_retrigger, coin_tick, win_countup_loop,
  big_win, mega_win, epic_win, max_win_reached, ui_click, menu_open, menu_close; music: music_base, music_fs.
