# FilmCraft Web (`film.lmk.one`)

Webowa wersja programu **FilmCraft** (nieliniowy edytor wideo i audio klasy Adobe Premiere Pro, napisany w Rust + WebAssembly + WebGPU/WebGL2 + WebCodecs) działająca bezpośrednio w przeglądarkce pod adresem:

👉 **[https://film.lmk.one](https://film.lmk.one)**  
*(oraz przez przekierowania: `https://lmk.one/film` i `https://lmk.one/filmcraft`)*

## Najważniejsze cechy tego wydania
- **Język polski domyślnie (`pl`)** – interfejs użytkownika, menu oraz ekran startowy są spolszczone od pierwszego uruchomienia.
- **Domyślny ciemny motyw (`Darkest`)** – profesjonalny, ciemny interfejs montażowy dopasowany do pracy z kolorem i wideo.
- **Natywna obsługa formatów wideo, audio i projektów** – obsługa kontenerów i kodeków (`MP4 / H.264 / HEVC / AV1`, `MOV / ProRes`, `MKV / WebM / VP8 / VP9`, `MXF / DNxHR`, `CinemaDNG`, `WAV / AIFF / FLAC / MP3 / AAC / Opus / AC-3`), napisów (`SRT / WebVTT /SCC / TTML`) oraz wymiany projektów (`.fcproj`, `Final Cut Pro XML`, `FCPXML`, `EDL`, `OpenTimelineIO`, `AAF`, `OMF`).
- **Akceleracja WebGPU + fallback WebGL2 (`?webgl`)** – automatyczne wykrywanie WebGPU z płynnym przełączeniem na kompozytor WebGL2 w razie potrzeby.
- **Zoptymalizowany pod szybkie ładowanie** – strumieniowe pobieranie WebAssembly z paskiem postępu na żywo oraz pre-kompresja `.gz` (`wasm-opt` + `gzip -9`).

## Parametry URL
- **Domyślnie:** [https://film.lmk.one/](https://film.lmk.one/) – otwiera wbudowany projekt demonstracyjny z osią czasu, klipami i efektami.
- **Czysty edytor:** [https://film.lmk.one/?new](https://film.lmk.one/?new) *(lub `?empty`)* – otwiera pusty edytor bez domyślnego projektu demonstracyjnego.
- **Dowolny plik bezpośrednio z sieci:** `https://film.lmk.one/?file=adres_do_pliku` – pozwala otworzyć projekt (`.fcproj`) lub zaimportować plik wideo/audio/obraz (`.mp4`, `.mov`, `.webm`, `.mkv`, `.wav`, `.mp3`, `.png` itd.) bezpośrednio z adresu URL i automatycznie utworzyć z niego sekwencję na osi czasu (działa również z linkami zewnętrznymi i chmurami takimi jak pCloud `filedn.eu` dzięki automatycznemu fallbackowi przez proxy CORS `https://lmk.one/api/cors`).
- **Wymuszenie WebGL2:** [https://film.lmk.one/?webgl](https://film.lmk.one/?webgl) – uruchamia aplikację w trybie kompatybilności WebGL2.
