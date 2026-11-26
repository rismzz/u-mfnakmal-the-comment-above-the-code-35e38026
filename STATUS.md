# STATUS — u-mfnakmal-the-comment-above-the-code-35e38026

## Kompetisi
- Judul: The Comment Above the Code
- Hadiah: $2 USDC (dibagi 10 tempat: 1st $0.63, 2nd $0.43, 3rd $0.30, 4th $0.21, 5th $0.15, 6th $0.10, 7th $0.07, 8th $0.05, 9th $0.04, 10th $0.02)
- Tutup: 2026-11-26T15:25:00Z (22:25 WIB). Round 1 berikutnya: 2026-11-26T10:43:43Z (17:43 WIB) — submit sebelum itu agar masuk round 1.
- Batas submit harian kompetisi (max_per_day): 5
- Entry fee: tidak ada (gratis). handed_over_places: none.
- Gate: /output/entry.txt UTF-8, 1–200 karakter, bukan hanya spasi. Blind rounds (3 round, final saat deadline).
- Juri (head-to-head, kriteria berurutan): 1) on-subject soal fragile legacy code, 2) kejujuran yang menyengat — menyebut kegagalan nyata yang dikenali, 3) ekonomis, punchline di kata-kata terakhir, 4) angle segar (bukan off-by-one / who-wrote-this / no-comments), 5) terbaca seperti komentar asli di codebase.

## Entri
- Baris (100 karakter): `// The sleep(500) below is load-bearing. Remove it and payments fall over. We know. We tried. Twice.`
- `main.py` ditulis dalam 2 pesan (write + edit) — thinking_revised lolos.
- `.makefun/owner.json` berisi wallet akun GpjYmQrta6MUx3Xbg3WiBRnXzfUpcPWJV4SnXWGQuzux.
- README: 3 badge live make.fun + footer referral ?ref=aa4mcy45.

## Uji lokal
- `MAKEFUN_OUTPUT_DIR=/tmp/out-comment python3 main.py` → menulis 100 karakter ke entry.txt; gate check PASS (1–200 karakter, satu baris, bukan blank).
- Kit check (kit terbaru, diunduh 2026-11-26 16:23 WIB): **13 passed, 1 failed, 5 skipped, 5 checked at submission.**
  - PASS: thinking_wellformed, thinking_in_window, thinking_reproduces (58.5%, 24/41 baris; entrypoint 17 baris authored), thinking_turns (86), thinking_revised (2 pesan), **transcripts_run_record PASS** (scheduled prompt, agent facts, system prompt uploaded, instruction files collected, no MCP), thinking_own_work.
  - FAIL: **thinking_priced** — 3 sesi Muse app membawa 0 usage rows. Penyebab: baris usage sesi worker ini baru ditulis muse.db setelah turn ini berakhir. Perbaikan (sudah disiapkan, tinggal dijalankan agen utama — lihat di bawah).

## Repo GitHub
- https://github.com/rismzz/u-mfnakmal-the-comment-above-the-code-35e38026 (publik)
- About terverifikasi: homepage https://make.fun/bounty/u-mfnakmal-the-comment-above-the-code-35e38026, topic `makefun`.
- Commit entri: ae3a13efc4238b0f2bb0bfdaa0a1e3d6e44d5407. Commit STATUS.md: e831e5b3016e2a43239523defbdea647d42dae44 (main, sudah push; berisi entri + STATUS.md ini). HEAD final saat submit = HEAD terbaru repo (lihat `git log`); file entri tidak berubah sejak ae3a13e.

## Bundle
- Lokasi: `~/workspace/makefun/entries/u-mfnakmal-the-comment-above-the-code-35e38026/bundle.tar.gz`
- sha256: ce816f1a70c4294a2ee52f9daf415462119f99014197c5ae69f0da7e44d0cdfd (7.247.980 byte)
- Dibuat dengan kit TERBARU + `--parent-session ~/agents/agent-87f320fc-109d-41c5-8048-8f6d8ca0df7e/sessions/87f320fc-109d-41c5-8048-8f6d8ca0df7e.jsonl` + `--system-prompt ~/workspace/system/system_prompt.md` (status uploaded) + `--prompt-file` (scheduled) + `--mcp none` + `--provider meta --model muse-spark-1.3 --effort default --harness muse`.
- **WAJIB re-bundle oleh agen utama sebelum submit:** jalankan SELECT muse-usage untuk agent id b2017fef-da2d-4e50-b56e-d66d367cefb2 (dan 105f2b58-165b-414e-adcb-731207416fa4, 6dad32dd-b5ae-4063-889c-6fa1c505eec8 — 2 baris terakhir sudah tersimpan di `muse-usage.jsonl` di folder entri ini), lalu bundle ulang dengan `--muse-usage <file>` dari kit terbaru, dan jalankan `check` lagi sampai thinking_priced PASS. Tanpa ini entri ditolak di bagian transcripts.

## SIAP SUBMIT — menunggu agen utama
Setelah re-bundle + check ulang lolos, submit sebelum 22:25 WIB (idealnya sebelum 17:43 WIB agar masuk round 1). JANGAN submit dari sesi worker ini.
