# companion-voices

The offline voice pack for **Companion**, Anuj Budhwar's personal Android app. The app downloads this pack once, checks its SHA-256 and unzips it to app-private storage. With it, the companion speaks with on-device neural TTS ([sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx)), even offline.

## Release `voices-v1`

Asset: `companion-voices-v1.zip`. Its SHA-256 is in `companion-voices-v1.zip.sha256` (attached to the release).

| Path in zip | What | Source | License |
|---|---|---|---|
| `kokoro/model.int8.onnx`, `kokoro/voices.bin`, `kokoro/tokens.txt`, `kokoro/lexicon-us-en.txt` | Kokoro-82M v1.0 multi-lang, int8, 54 speakers (the app uses 10 of them as character voices) | [hexgrad/Kokoro-82M](https://huggingface.co/hexgrad/Kokoro-82M), converted by k2-fsa (`kokoro-int8-multi-lang-v1_0`) | **Apache-2.0** (`LICENSES/KOKORO-LICENSE-Apache-2.0.txt`) |
| `piper-hi-f/` | Piper VITS hi_IN *priyamvada* (medium, int8), female Hindi voice | [rhasspy/piper](https://github.com/rhasspy/piper) voice by PravalX, dataset AI4Bharat indicnlp_corpus, converted by k2-fsa | **CC BY-NC-SA 4.0** per its model card (`LICENSES/PIPER-hi_IN-priyamvada-MODEL_CARD.txt`, `LICENSES/CC-BY-NC-SA-4.0.txt`) |
| `piper-hi-m/` | Piper VITS hi_IN *pratham* (medium, int8), male Hindi voice | same as above | **CC BY-NC-SA 4.0** per its model card (`LICENSES/PIPER-hi_IN-pratham-MODEL_CARD.txt`) |
| `espeak-ng-data/` | espeak-ng phoneme data, trimmed to the English and Hindi dictionaries | [espeak-ng](https://github.com/espeak-ng/espeak-ng) | **GPL-3.0** (`LICENSES/ESPEAK-NG-COPYING-GPL-3.0.txt`) |
| `manifest.json` | Pack layout and file sizes | this repo | - |

The Piper Hindi voices are licensed **non-commercial, share-alike** (CC BY-NC-SA 4.0). This pack is for personal, non-commercial use. Attribution: voices by PravalX, trained on AI4Bharat data. Nothing in this pack was changed except the format conversion done by k2-fsa and trimming unused espeak-ng dictionaries.

Character voice mapping used by the app (Kokoro speaker ids): Sakura af_bella (2), Hana af_nicole (6), Lilith af_river (8), Luna af_kore (5), Kira af_sky (10), Kai am_onyx (17), Ren am_puck (18), Haru am_echo (12), Sora hm_omega (33), Ryuu am_fenrir (14).
