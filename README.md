# **Russian Open Text To Speech (TTS) Dataset**

Arguably the largest public Russian TTS dataset up to date:
- ~5 000 voices;
- ~13 000 hours;
- **(new!)** A new domain - public speech with ~3 000 hours;
- **(new!)** A new domain - radio with ~10 000 hours;
- Speaker labels for new domains are coming soon!

Prove [us](mailto:open_stt@googlegroups.com) wrong!
Open issues, collaborate, submit a PR, contribute, share your datasets!
Let's make TTS/STT in Russian (and more) as open and available as CV models.

**Table of contents**
  - [Downloads](https://github.com/snakers4/open_tts/#downloads)
    - [Links](https://github.com/snakers4/open_tts/#links)
    - [Download-instructions](https://github.com/snakers4/open_tts/#download-instructions)
    - [End-to-end download scripts](https://github.com/snakers4/open_tts/#end-to-end-download-scripts)
  - [Annotation methodology](https://github.com/snakers4/open_tts/#annotation-methodology)
  - [Contacts](https://github.com/snakers4/open_tts/#contacts)
  - [License](https://github.com/snakers4/open_tts/#license)
  - [Donations](https://github.com/snakers4/open_tts/#donations)

# **Updates**

## **_Update 2019-11-04_**

**New train datasets added:**

- 10,430 hours radio_v4;
- 2,709 hours public_speech;
- 154 hours radio_v4_add;
- 5% sample of all new datasets with annotation.
- Speaker labels are coming soon!

<details>
  <summary>Click to expand</summary>

    ## **_Update 2019-06-28_**

    `russian_young_male_1` added (~43 hours)
  
    ## **_Update 2019-05-24_**

    It's alive!
    Looking for collaborators)
    
</details>

# **Downloads**

# **Links**

~~Meta data [file](https://ru-open-tts.ams3.digitaloceanspaces.com/public_tts_df_02.csv).~~**Coming soon!**

| Voice                      | Clips  | Hours | GB  | Comment  | Links          | Md5sum                             |
|----------------------------|--------|-------|-----|----------|---------------|------------------------------------|
| 5% of radio + public_speech | 469797 | 665 | 66,7| | [link](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/radio_pspeech_sample_mp3.tar.gz), [manifest](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/radio_pspeech_sample_manifest.csv) | `84397631475426f505babbb73b4197d9` |
| radio                   | 7,603,192| 10,430| 1,195 |      | [link](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/radio_v4_mp3.tar.gz), [manifest](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/radio_v4_manifest.csv), [labels](https://forms.gle/nosMaNgj8MWKm99d9) | `7c2273a5b8c3cc10df3754dbe9c783e1` |
| public_speech              | 1,700,060| 2,709 | 301 |        | [link](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/public_speech_mp3.tar.gz), [manifest](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/public_speech_manifest.csv), [labels](https://forms.gle/nosMaNgj8MWKm99d9) | `d41f3f21d3cb9328de3cd6a530a70832` |
| radio_add               |  92,679  |   157 | 18  |        | [link](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/radio_v4_add_mp3.tar.gz), [manifest](https://ru-open-stt.ams3.cdn.digitaloceanspaces.com/radio_v4_add_manifest.csv), [labels](https://forms.gle/nosMaNgj8MWKm99d9) | `ae00489678836b92e3a65d2ee8b51960` |
| russian_middle_aged_male_1 | 45,311 | 64    | 9.7 | Rnnoise  | [link](https://ru-open-tts.ams3.digitaloceanspaces.com/russian_middle_aged_male_1.tar.gz)      | `f1157d6dfd07c302c23cfe7dcb0298f5` |
| russian_middle_aged_male_2 | 46,684 | 38    | 6.0 | Rnnoise  | [link](https://ru-open-tts.ams3.digitaloceanspaces.com/russian_middle_aged_male_2.tar.gz)      | `059ab6b3e5fa77319f7bf20e594fc133` |
| russian_young_male_1 (tts_2)     | 118,536 | 43    |  4.9   |          | [link](https://ru-open-tts.ams3.digitaloceanspaces.com/tts_2.tar.gz)      | `403c90662beb51ac9a39d64b879e0f1b` |
| total                      | 9,606,462 | 13,446 |  1,535 |          |               |  |

## **Download instructions**

### End to end

`download.sh` or `download.py` with this config [file]((https://github.com/snakers4/open_tts/blob/master/md5sum.lst)). Please check the config first.

### Manually

1. Download each dataset separately:

  Via `wget`
  ```
  wget https://ru-open-stt.ams3.digitaloceanspaces.com/some_file
  ```

  For multi-threaded downloads use aria2 with `-x` flag, i.e.
  ```
  aria2c -c -x5 https://ru-open-stt.ams3.digitaloceanspaces.com/some_file
  ```

2. Download the meta data.

# **Data collection / denoising / normalization methodology**
The dataset is compiled using open domain sources.

## Russian_middle_aged/young_male
Then the dataset is cleaned using the best ASR engine we have at hand and only items with `CER` less than `0.1` are left.

Then where applicable:
- Spectral [gating](https://github.com/timsainb/noisereduce) / de-noising is applied;
- Rnnoise is [applied](https://github.com/xiph/rnnoise/issues/69);

All files are normalized as follows:
- Converted to mono, if necessary;
- Converted to 22 kHz sampling rate, if necessary;
- Stored as 16-bit integers;

22 kHz was chosen as an optimal rate used in the literature, though in real applications as low as 8kHz may suffice.

## Radio/Public Speech

All files are normalized for easier / faster runtime augmentations and processing as follows:

- Converted to mono, if necessary;
- Converted to 16 kHz sampling rate, if necessary;
- Stored as 32 kbps `mp3`;

# **Contacts**

Please contact us [here](mailto:open_stt@googlegroups.com) or just create a GitHub issue!

**Authors in alphabetic order:**
- Anna Slizhikova;
- Alexander Veysov;
- Dmitry Voronin;
- Yuri Baburov;

# **License**
Dual license, cc-by-nc and commercial usage available after agreement with dataset authors.


# **Donations**

[Donate](https://buymeacoff.ee/8oneCIN) (each coffee pays for several full downloads) or via [open_collective](https://opencollective.com/open_stt) / use our DO referral [link](https://sohabr.net/habr/post/357748/) to help.

