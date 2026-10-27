# Karmienia

Dziennik karmienia i snu niemowlaka — aplikacja na iPhone'a (PWA), hostowana na Netlify.

## Struktura
- `public/` – aplikacja (jeden plik `index.html`, service worker, ikony)
- `netlify/functions/sync.mjs` – wspólne dane dla kilku telefonów (Netlify Blobs)
- `netlify.toml` – ustawienia Netlify (publikuje `public/`, funkcje z `netlify/functions/`)

## Wspólne dane na dwóch telefonach
1. Telefon 1: przewiń na dół → **Utwórz kod rodziny** → **Wyślij kod**.
2. Telefon 2: przewiń na dół → wpisz kod w polu „Mam kod z drugiego telefonu” → **Połącz**.

Dane każdej rodziny są zapisane pod skrótem (SHA-256) kodu. Kto zna kod, widzi i zmienia wpisy,
więc kodu nie należy publikować. Wpisy zrobione bez internetu czekają w telefonie i wysyłają się później.
