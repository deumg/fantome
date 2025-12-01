"Patches" for converting track 03 and 07 from single mastering to album mastering

---

The "patches" in this directory, as hinted with their extensions, are "XOR-encrypted". The "encryption keys" used are (portions of) the (signed, little-endian) raw streams of the single-mastering version of the corresponding tracks *after the "aligning preparation" for the conversion desired*, i.e., what can be obtained with:

```
sox original/03.flac aligned/03.flac pad 13443s trim 0 26711304s
sox aligned/03.flac aligned/03.raw
```
```
sox original/07.flac aligned/07.flac pad 25645s trim 0 32481677s
sox aligned/07.flac aligned/07.raw
```

The MD5s of the original tracks expected are:
```
444897bda4f89d63a86d09a82f3d057d
38ea741aa0c32ff50d49e4556c126f40
```

And the MD5s of the "aligned" output / "encryption keys" would be:
```
1feb8ea1695c8049a1a3cc0f5a504030
545a772cce707d71c5e89c426d768730
```

---

With the "encryption keys" you can decrypt the encrypted patches with a program that XOR a file against another. For example:
```
# Usage: xor encrypted_file encryption_key output_path
xor 03.flac.xor aligned/03.raw patches/03.flac
xor 07.flac.xor aligned/07.raw patches/07.flac
```

Finally, apply the patches to the "aligned" FLAC files produced earlier:
```
sox -m aligned/03.flac -v -1 patches/03.flac 03.flac
sox -m aligned/07.flac -v -1 patches/07.flac 07.flac
```

The MD5s of the final result (i.e. the album-mastering version of the tracks) would be:
```
81bf91492e4454f91c9eb8d3a740d1d6
e65ae05f9876566cd7988204788364ff
```
