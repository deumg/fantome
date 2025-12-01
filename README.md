"Watermark" Removal "Patches" for the album Fantôme by Hikaru Utada (24 bit / 96 kHz)

---

**DISCLAIMER**:
These are not actual tracks from the respective stores,
but "differences" between those tracks,
which are believed to be watermarked,
and the version that is believed to be non-watermarked.
In other words they are meaningful only for someone that already has purchased (or in possession) one of the sets.
It would be extremely wrongful for these to be taken down for DMCA reasons,
especially when this does not need to exist if the Universal Music Group has never come up with such hideous thing
(which deprives people that have purchased the music of what they deserve).

---

The MD5s (of the raw PCM samples) of the version that is believed to be non-watermarked:
```
9f72d23c87a824023ae635b93d1cfec1
a281e4be96c1ed232da7064f7fb00b85
81bf91492e4454f91c9eb8d3a740d1d6
fd433c491e57290493219d9a139e772d
993715faeb961f726bebad454657c394
91a25760c016ac04ba6ad9faf747b025
e65ae05f9876566cd7988204788364ff
0e64b2bce0c7b0454fae8ed36f85a013
86fde5ed54254a395783b946208e41d5
50c143456bedd85c618ca2df849beb91
9d39087dea3bbdffe936a320cf84f5f3
```

---

The "patches" in `qobuz` and `japan` were created by "subtracting" the non-watermarked version from the respective watermarked version,
in other words you can obtain the the non-watermarked version by subtracting the corresponding "patches" from the watermarked version you have.
For example:
```
sox -m watermarked.flac -v -1 patch.flac non-watermarked.flac
```
So I suppose you can say that these "patches" are the "watermarks" themselves.

---

The MD5s of the version that is currently available on Qobuz:
```
0d9f9393bce78412596f1a8cfddb2279
ba2a64c0f667a0e02b038c5dca823fdd
b4689688dfbd8d9e07516d77748f727b
7aebdf312f6e57f621151ac66afc35b9
3a48c1486c24e82ad0624fe1e4eedabd
3849b5cb8072eecb339d5bb4db36e72d
b969dcf37c9b9d2aa29ccecaabd44814
0188df5612345ebef97b53189479334f
3b403a96e3a445051cb21fefb6d790a6
d4fb340bc7c6bcfd2e1ad76a76fcd68e
7ccc2449611bf523e88578a1f92be9e3
```
Patches in `qobuz` are for this version.

---

The MD5s of the version that is currently available on OTOTOY, レコチョク, and *probably* (unconfirmed) mora and other stores in Japan:
```
51f719808f2c97f99d88dcdbfd295e89
7ba2cc7ae884a567caae74a3330ce6d8
26270643e3935053b85bbbf3723053be
b3f06ac95d830845b8b1e2717de0855b
f8eeacbc12cba79e094bacadc70311d0
7221461bffe4d44b3cf0a32dd726e699
03b89a17ae967df2d0227141615db3eb
7fa0d61389160b0d409e64bf6b7fb0d2
9c283bcb50e1ea386847e5add56205c4
516ccc9d1250ed555827a3fb778767e7
67f0dfbb9d1c26f1efab0eff64f5f682
```
Patches in `japan` are for this version.
(As you may have noticed, these patches are much larger than those in `qobuz`,
which, as far as i know, means that the differences are to some extent more significant.
Yet for reasons I still believe that this Japan version is watermarked, and that it was likely just
produced with a different version (as in generation / variant) of watermarking mechanism, instead of
a watermarked version that is produced from a different master.)

---

The MD5s of the version that *was once available* on OTOTOY (now replaced with the version just mentioned above),
and *maybe* (unconfirmed) other stores in Japan:
```
9f416738799b8b987da3354db74c41a6
7f5e084fd3db1b1aae415aa2df099446
9afd2836c9a650a4a2da31f452cc0ad6
8e936d11fdd07403a4aac2b86e79e27b
11a68b1e27b143a864babc05f09e9da2
b6c81d2f8500743240e65ba5eb5d3945
8c71e97a716a7a5d8d832684b928e360
aec9b49030216617da6c3de0c5c7e603
7accca71511d80fc7f93c9f0e44dcfc3
3e8b36c0761c7480d4f59adb0e640fbc
35632551228a85b9cea313f87f0582fc
```
Patches in `ototoy` are for this version, but they were created by subtracting "the Japan version" from this version.
In other words, if you would like to get to non-watermarked version from that, you will need to do e.g.:
```
sox -m ototoy.flac -v -1 ototoy_patch.flac japan.flac
sox -m japan.flac -v -1 japan_patch.flac non-watermarked.flac
```
In fact you can get to any of the version mentioned from another mentioned one.
All you need is a different series of `sox -m` commands, just that in some with `-v 1` instead of `-v -1`.
(Note that `-v 1` makes a difference for `sox -m`, so do not think that you will get the same result with it omitted. Check out the man page for details.)

---

As far as I know, on at least one of the store (which is in China), you would get the non-watermarked version,
except that track 03 (花束を君に) and 07 (真夏の通り雨), although also (essentially for certain) non-watermarked, are of different "cut" and mastering.
This is because these two tracks were available as digital singles (at 24/96). It is very common for stores in
China to have this sort of miss. Their lengths in samples are:
```
26844160
32699520
```
whereas the lengths in samples of the respective album "cuts" are:
```
26711304
32481677
```
I am planning to share also methods and "patches" for converting these single "cuts" to their respective album "cuts".
However, because these different versions of "cuts" are of different mastering, the "differences" between them are very audible.
Some segments of the "patches" might even sound very "normal". So I am still thinking about it (because of DMCA crap or so).
Probably I would need to have them XOR-encrypted or so using the single "cuts" as keys before I share them.

---

If you have some other version(s) that you would like me to make patches for (or examine), you are welcomed share them with me. My Gmail is "deumg dot w".
(Better not post a link in an Issue, I think.)

If you are someone from the mastering studio or so, you are more than welcomed to share with me the MD5s (with lengths in samples) of actual original tracks
(in case the version believed to be non-watermarked here is not actually non-watermarked). FLAC files would be even better, of course.

**As hinted above, the version that I currently believe to be non-watermarked is not leaked from some secret channel, but publicly available for purchase on at
least one digital store.** Also, (for obvious reasons) I myself have made **multiple** purchases of this (digital) album.

---

P.S. MD5s of the raw PCM samples can be obtained with `metaflac --show-md5sum`.
If you get all zeroes with that, you can re-encode your FLAC files to have them fixed.
