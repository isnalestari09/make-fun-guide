# SUBMISSION CHECKLIST — Bring the humans again (make.fun)

> ⚠️ File ini HANYA panduan internal Dima. File ini boleh ada di repo, tapi
> yang dinilai make.fun adalah `README.md` + `screenshot.png` + transkrip sesi.
> Jangan submit sebelum semua kotak di bawah ini dicentang.

## Fakta bounty (terverifikasi dari https://make.fun/bounty/bring-the-humans-02)

- **Slug:** `bring-the-humans-02`
- **Hadiah:** $1.000 USDC (escrow Solana, sudah terkunci sejak 18 Nov 2026)
  - Juara 1: $150 · Juara 2: $80 · Juara 3: $50
  - Peringkat 4–10: $20 · 11–25: $17 · 26–50: $13
- **Deadline entry:** Sabtu, 21 Nov 2026, 17:30 WIB (10:30 UTC)
- **Hasil diumumkan:** paling lambat 6 Des 2026
- **Leader saat ini (18 Nov 2026):** @tidy-fox-11 dengan 16 signup terverifikasi.
  Target Dima: kalahkan 16 itu untuk juara 1; masuk 10 besar = $20.
- **Yang dihitung:** jumlah signup manusia terverifikasi lewat link referral
  Dima. Signup palsu/bot tidak dihitung; ada penahanan review 24 jam.
- **Harness:** referral/v1 — entry berupa repo GitHub publik saja
  (tidak ada source bundle). Transkrip sesi agen yang menulis panduan ini
  wajib diunggah bersama entry.

## 1. Yang harus Dima berikan (tidak bisa ditebak)

| # | Yang dibutuhkan | Dari mana mendapatkannya |
|---|---|---|
| 1 | **Kode referral make.fun Dima** | Akun make.fun Dima → profil / `GET /api/me/referrals` → field `code`. Contoh: kalau kodenya `abc123`, linknya `https://make.fun/r/abc123` |
| 2 | **Username GitHub Dima** | Akun GitHub yang sudah terhubung (linked) ke akun make.fun Dima. Cek di profil make.fun: harus tertulis GitHub terhubung. |
| 3 | **Nama repo (opsional)** | Default di sini: `make-fun-guide`. Boleh ganti, tapi samakan di badge README. |

## 2. Ganti placeholder di README.md (WAJIB sebelum submit)

Cari dan ganti semua kemunculan ini di `README.md`:

| Placeholder | Ganti dengan | Di mana saja |
|---|---|---|
| `[GITHUB_OWNER]` | username GitHub Dima | Badge rank, badge reward, dan semua link `github.com/[GITHUB_OWNER]/...` |
| `[REFERRAL_CODE]` | kode referral Dima | Link `https://make.fun/r/[REFERRAL_CODE]`, link `https://make.fun/?ref=[REFERRAL_CODE]...`, dan footer "Entered on make.fun" |
| `make-fun-guide` | nama repo, kalau diganti | Badge rank/reward dan link GitHub |

Perintah cepat (dari dalam folder repo, setelah tahu nilainya):

```sh
# Ganti OWNER, REPO, dan CODE dengan nilai asli Dima, lalu jalankan:
sed -i 's/\[GITHUB_OWNER\]/OWNER_ASLI/g; s/\[REFERRAL_CODE\]/KODE_ASLI/g' README.md
grep -n 'REFERRAL_CODE\|GITHUB_OWNER' README.md   # harus KOSONG hasilnya
```

**Kenapa ini wajib:** pemeriksaan `repo_readme` make.fun GAGAL kalau URL badge
masih berisi placeholder owner/repo, dan README harus menyebutkan kode
referral asli (kode telanjang, `/r/<code>`, atau `?ref=<code>`).

## 3. Buat repo GitHub-nya

- Buat repo **publik baru** di akun GitHub yang terhubung ke make.fun Dima,
  **setelah kompetisi dibuka** (dibuka 18 Nov 2026 — repo yang dibuat
  sekarang sudah memenuhi syarat "created after the competition opens").
- Nama repo: `make-fun-guide` (atau nama yang Dima pilih).
- Push file-file ini ke root repo: `README.md`, `LICENSE`, `screenshot.png`
  (screenshot diganti dulu, lihat langkah 5).
- JANGAN letakkan panduan di `.github/README.md` — harus `README.md` di root,
  tepat bernama begitu, max 2 MB.

## 4. Atur About repo di GitHub

Jalankan (ganti `OWNER` / `REPO` / ringkasan):

```sh
gh repo edit OWNER/REPO \
  --description 'A beginner-friendly guide to make.fun: how AI agents earn USDC by winning coding bounties. Built by an AI agent for make.fun'"'"'s "Bring the humans again" bounty, $1,000 in USDC.' \
  --homepage 'https://make.fun/bounty/bring-the-humans-02' \
  --add-topic 'makefun,ai-agents,bounties,growth'
```

Atau atur manual di GitHub: repo → ⚙️ About → Website =
`https://make.fun/bounty/bring-the-humans-02`, Topics =
`makefun`, `ai-agents`, `bounties`, `growth`.

## 5. Ganti screenshot.png dengan screenshot ASLI

- `screenshot.png` yang ada di folder ini sekarang adalah **PLACEHOLDER**
  (gambar teks "ganti dengan screenshot asli"). File ini HANYA supaya
  struktur repo lengkap saat dicek lokal — **jangan submit dengan file ini.**
- Setelah repo publik di GitHub: buka halaman repo itu di browser,
  screenshot halaman repo dengan README yang tampil, simpan sebagai
  `screenshot.png` di root repo (PNG/JPEG/WebP, max 8 MB, max 16.000.000 piksel),
  lalu commit + push.
- Nama file harus tepat `screenshot.png`.

## 6. Transkrip sesi agen

- Entry ini wajib menyertakan **transkrip sesi agen yang menulis panduan ini**
  (bundle dari kit make.fun: `node cli/makefun.mjs bundle`, atau file
  transkrip lepas). Simpan/unggah transkrip itu saat submit.
- Jangan menulis ulang / membuat transkrip dari ingatan — pakai log sesi
  asli dari harness yang membangun entry ini.

## 7. Submit

- Submit lewat kit make.fun sebelum **21 Nov 2026, 17:30 WIB**:
  `node cli/makefun.mjs submit --competition bring-the-humans-02
  --repo-url https://github.com/OWNER/REPO --commit <SHA 40 karakter>
  --title "make-fun-guide" --bundle <bundle> --keypair <keypair>`
  (atau lewat web UI make.fun).
- Setelah submit, pantau status entry sampai pemeriksaan `repo_readme`
  lolos. Kalau gagal, perbaiki README, commit, push, lalu submit commit
  baru.
- Repo harus **tetap publik, pemilik dan kode referral yang sama** sampai
  pemeriksaan akhir selesai.

## 8. Setelah submit — cara menang

- Sebarkan link referral Dima (https://make.fun/r/KODE_ASLI) + link repo
  ini ke orang yang benar-benar memakai AI agent: developer, pelajar
  coding, komunitas AI. Target: **lebih dari 16 signup** (leader saat ini).
- Hanya signup manusia terverifikasi yang dihitung. Jangan beli / buat
  akun palsu — tidak dihitung dan bisa didiskualifikasi.

## Status file di folder ini

- [x] `README.md` — ditulis, 3 badge make.fun lengkap, placeholder ditandai
- [x] `LICENSE` — MIT (OSI-approved)
- [x] `screenshot.png` — PLACEHOLDER, wajib diganti dengan screenshot asli (langkah 5)
- [x] `SUBMISSION_CHECKLIST.md` — file ini
- [ ] Kode referral Dima — BELUM ADA (butuh dari Dima)
- [ ] Username GitHub Dima — BELUM ADA (butuh dari Dima)
- [ ] Repo GitHub dibuat + dipush — BELUM (butuh akun GitHub Dima)
- [ ] Screenshot asli — BELUM (butuh repo publik dulu)
- [ ] Submit ke make.fun — BELUM
