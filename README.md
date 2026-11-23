# eFutsal 3D

Prototype game futsal 5v5 modular berbasis Three.js ES Modules. Pemain, arena, dan bola dibuat procedural sehingga tidak membutuhkan model asset eksternal.


## Isi proyek
- `index.html`: UI/menu dan HUD
- `css/style.css`: layout responsif + kontrol mobile
- `js/main.js`: boot, input, game loop
- `js/data/teamsAndPlayers.js`: roster dan tim
- `js/world/arena3d.js`: arena Three.js
- `js/gameplay/futsalEngine.js`: movement, ball, bot sederhana, scoring
- `js/gameplay/aiController.js`: extension point AI
- `js/gameplay/tieBreaker.js`: helper tie-break
- `js/network/onlineMode.js`: PeerJS connection wrapper + fallback
- `js/ui/teamCustomizer.js`, `adminPanel.js`: squad/admin

## Jalankan lokal
ES Modules dan CDN tidak berjalan konsisten bila file dibuka sebagai `file://`. Jalankan web server lokal dari folder proyek:


### Python
```bash
python -m http.server 8000
```
Buka `http://localhost:8000`.

### VS Code
Install Live Server, klik kanan `index.html` → Open with Live Server.

## GitHub Pages
1. Upload seluruh isi folder ini ke repository GitHub (jangan hanya `index.html`).
2. Repository Settings → Pages → Deploy from branch.
3. Pilih branch `main`, folder `/root`, lalu Save.
4. Buka URL Pages setelah deployment selesai. CDN Three.js/PeerJS memerlukan internet.


## ZIP
Dari folder yang berisi `efutsal-3d/`:
```bash
zip -r efutsal-3d.zip efutsal-3d
```
Windows: klik kanan folder `efutsal-3d` → Send to → Compressed (zipped) folder.


## Controls
- WASD / arrow: gerak
- J / Z / Space: pass
- K / X: through pass
- L / Enter: shoot
- Q / E: switch player
- Shift: sprint
- Mobile: joystick + tombol aksi

## Catatan scope prototype
Ini prototype fondasi gameplay, bukan simulasi eFootball penuh. Beberapa fitur spesifikasi (foul/handball & akumulasi foul, kick-in/corner/free kick/second penalty, halftime side-switch, extra-time/penalty shootout/suit yang terintegrasi, curve trajectory visual, stamina UI, online authoritative sync, squad assignment ke engine, editor statistik pemain, dan kontrol manual GK online) belum diimplementasikan secara penuh. Online saat ini berupa wrapper koneksi PeerJS dan fallback bot, bukan multiplayer state-sync siap kompetitif. Browser/WebGL/CDN bisa gagal karena perangkat, jaringan, atau kebijakan browser; aplikasi menampilkan fallback.
