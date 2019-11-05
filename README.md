**Will be updated shortly. Stay tuned!**

# **Russian Open Text To Speech (TTS) Dataset**

Arguably the largest public Russian TTS dataset up to date:
- 3 voices (male);
- 145 hours;

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

## **_Update 2019-05-24_**

It's alive!
Looking for collaborators)

<details>
  <summary>Click to expand</summary>
  Nothing here yet.
</details>

## ** _Update 2019-06-28_**

`russian_young_male_1` added (~43 hours)
Meta [file](https://ru-open-tts.ams3.digitaloceanspaces.com/public_tts_df_02.csv) renewed 


# **Downloads**

# **Links**

Meta data [file](https://ru-open-tts.ams3.digitaloceanspaces.com/public_tts_df_02.csv).

| Voice                      | Clips  | Hours | GB  | Comment  | Link          | Md5sum                             |
|----------------------------|--------|-------|-----|----------|---------------|------------------------------------|
| russian_middle_aged_male_1 | 45,311 | 64    | 9.7 | Rnnoise  | [link](https://ru-open-tts.ams3.digitaloceanspaces.com/russian_middle_aged_male_1.tar.gz)      | `f1157d6dfd07c302c23cfe7dcb0298f5` |
| russian_middle_aged_male_2 | 46,684 | 38    | 6.0 | Rnnoise  | [link](https://ru-open-tts.ams3.digitaloceanspaces.com/russian_middle_aged_male_2.tar.gz)      | `059ab6b3e5fa77319f7bf20e594fc133` |
| russian_young_male_1 (tts_2)     | 118,536 | 43    |  4.9   |          | [link](https://ru-open-tts.ams3.digitaloceanspaces.com/tts_2.tar.gz)      | `403c90662beb51ac9a39d64b879e0f1b` |
| total                      | 210,531  | 145   |  20.6   |          |               |  |

## **Download instructions**

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


## **End to end download scripts**

You can use this [script](https://github.com/snakers4/open_tts/blob/master/download.sh) with this config [file](https://github.com/snakers4/open_tts/blob/master/md5sum.lst).
Please check the config first.

# **Data collection / denoising / normalization methodology**

The dataset is compiled using open domain sources.
Then the dataset is cleaned using the best ASR engine we have at hand and only items with `CER` less than `0.1` are left.

Then where applicable:
- Spectral [gating](https://github.com/timsainb/noisereduce) / de-noising is applied;
- Rnnoise is [applied](https://github.com/xiph/rnnoise/issues/69);

All files are normalized as follows:
- Converted to mono, if necessary;
- Converted to 22 kHz sampling rate, if necessary;
- Stored as 16-bit integers;

22 kHz was chosen as an optimal rate used in the literature, though in real applications as low as 8kHz may suffice.

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

[Donate](https://buymeacoff.ee/8oneCIN) (each coffee pays for several full downloads) / use our DO referral [link](https://sohabr.net/habr/post/357748/) to help.

