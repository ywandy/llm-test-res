# 固定 ASR 音频

`zh-short.mp3` 是 macOS `Tingting` 语音合成的短句：

```text
AIHub语音识别验收测试
```

生成命令：

```bash
fixture_tmp_dir="$(mktemp -d)"
say -v Tingting "AIHub语音识别验收测试" -o "$fixture_tmp_dir/source.aiff"
ffmpeg -y -i "$fixture_tmp_dir/source.aiff" \
  -ar 16000 -ac 1 -codec:a libmp3lame -b:a 64k \
  server/tests/channel-acceptance/fixtures/audio/zh-short.mp3
```

当前文件属性：MP3、16000 Hz、单声道、约 2.343 秒。SHA-256：

```text
c2cccf9270fe5c7f80e6db4e3e4a7ebf155538e01503145d6cdea5159ee88a07
```

素材只包含合成语音，不包含个人录音、业务数据或受版权保护内容。
