# ⚔️ Cacaturan ⚔️

Game catur *offline* yang dibuat pake kekuatan vanilla JavaScript, dibumbui dengan kearifan lokal Sunda. Awas, wani curang dikadek!

## Tentang Project "Halahhh, Barodok Gini Maen Teh"

"Cacaturan" ini adalah implementasi game catur sederhana yang semua *logic*-nya dibungkus rapi dalam satu file HTML pake vanilla JavaScript. Gak ada *framework*, gak ada *library* aneh-aneh, cuma HTML, CSS, dan JS murni.

Project ini jadi bukti kalo buat bikin sesuatu yang fungsional dan keren, lo gak selalu butuh *toolchain* yang ribet. Cukup logika yang jalan dan sentuhan humor yang... unik.

## Fitur Unggulan

- ✅ **Gameplay Catur Lengkap (ya iyalah):** Semua bidak jalan sesuai aturan. Gak ada kuda bisa jalan lurus di sini.
- ✅ **UI Interaktif:** Bisa klik bidak, liat kemungkinan langkah yang valid (yang ijo-ijo itu), dan tentu saja, makan bidak lawan.
- ✅ **Deteksi Skak, Skakmat, dan Stalemate:** Gamenya tau kapan raja lo dalam bahaya, kapan lo udah kalah telak, dan kapan permainannya seri karena sama-sama cupu.
- ✅ **Tombol 'Mbitan' (Undo):** Salah langkah? Nyesel? Tinggal klik "Mbitan". Tapi inget, di kehidupan nyata gak ada tombol undo.
- ✅ **Tombol 'Miti Deui' (Reset):** Udah pusing dan pengen nyerah? Klik aja ini. Mental aman.
- ✅ **History Langkah:** Biar gak bisa ngeles "eh tadi gue jalan mana ya?". Semua langkah tercatat rapi.
- ✅ **Desain Responsif:** Harusnya sih aman dibuka di HP, tapi jangan di-resize kayak orang bar-bar juga.

## Tech Stack (Gak Pake Ribet)

Gak pake library aneh-aneh, ini murni kekuatan doa dan:

- **HTML5:** Buat struktur papannya.
- **CSS3:** Bikin tampilannya cakep pake `grid`, `linear-gradient`, dan `box-shadow`. Biar gak keliatan kayak project kuliah semester 2.
- **JavaScript (ES6):** Nah, ini otaknya. Semua logic dibungkus dalam satu `class ChessGame`, biar keliatan pro dikit dan gampang di-manage.

## Cara Menjalankan

Gampang banget, lebih gampang dari ngalahin elo main catur (canda, bos).

1.  *Clone* repo ini (kalo udah lo jadiin repo di GitHub).
2.  Buka file `chess.html` di browser favorit lo (Chrome, Firefox, Safari, asal jangan Internet Explorer aja).
3.  Udah. Gitu doang. Gak perlu `npm install` sampe subuh. Langsung mainkan dan buktikan siapa yang paling *barodok*.

## Struktur Kode (Bedah Dapur)

Buat lo yang *fullstack developer*, pasti penasaran gimana isinya kan? Semua keajaiban terjadi di dalam tag `<script>`.

-   **`class ChessGame`**: Ini jantungnya. Semua state, dari posisi bidak (`this.board`), giliran siapa (`this.currentPlayer`), sampe riwayat langkah (`this.moveHistory`), diurus di sini.
    -   `constructor()`: Menginisialisasi papan, UI, dan semua state awal.
    -   `initializeBoard()`: Setup posisi awal bidak "Bodas" dan "Magrib".
    -   `renderBoard()`: Fungsi krusial yang nge-gambar ulang papan setiap ada perubahan. Dia yang nampilin bidak, highlight kotak yang dipilih, dan nunjukin langkah valid.
    -   `handleSquareClick()`: Logic utama interaksi user. Nentuin kapan harus milih bidak, kapan harus jalan, kapan harus batal milih.
    -   `getValidMoves(row, col)`: Otak dari semua logic pergerakan. Di sini semua aturan catur dari pion sampe raja di-handle, termasuk nge-filter langkah yang bikin raja sendiri skak.
    -   `makeMove(...)`: Eksekusi langkah, update state papan, ganti giliran pemain, dan ngecek kondisi *game over*.
    -   `checkGameOver()`: Ngecek apakah terjadi Skakmat atau Stalemate.
    -   `undoLastMove()` & `resetGame()`: Fungsi buat tombol "Mbitan" dan "Miti deui".

## Rencana Pengembangan (Kerjaan Gak Ada Abisnya)

Kalo lo gabut lagi, ini beberapa ide buat ngembangin "Cacaturan" biar makin sangar:

1.  **Refactor CSS/JS:** Udah bagus sih, tapi sebagai *fullstack dev* sejati, lo pasti gatel pengen misahin CSS sama JS ke file eksternal. Biar lebih *clean* dan *maintainable*.
2.  **Multiplayer Online:** Ini tantangan seru. Biar bisa main lawan orang beneran, bukan cuma sama diri sendiri.
    -   **Backend:** Pake Node.js (Express/Fastify) atau Go.
    -   **Real-time:** Pake **WebSocket** (misal, pake library `Socket.IO`) buat ngirim data langkah antar pemain secara *real-time*.
    -   **API:** Bikin REST API buat *matchmaking*, *history* pertandingan, dll.
3.  **Lawan AI (Bot Cupu):** Tambahin mode Player vs Computer. Gak perlu canggih-canggih dulu, pake algoritma **Minimax** sederhana aja udah cukup buat bikin lawan yang lumayan bikin mikir.
4.  **Database:** Kalo udah multiplayer, simpen *history* match dan data user di database. Postgres atau MongoDB? Terserah mazhab lo.
5.  **Pawn Promotion Choice:** Sekarang pion kalo promosi langsung jadi Ratu (`♕`/`♛`). Kasih pilihan dong, mau jadi Benteng, Kuda, atau Gajah. Biar makin strategis.

---
Dibuat dengan sedikit kopi dan banyak cireng.
