# pico_usb_audio_loopback
Raspberry Pi Picoとtinyusbを使ったUSB Audioのループバックデバイスです。
PCの音声を別途ソフトをインストールすることなくハードウェアループバックで録音可能です。  
録音品質は24bit/48kHz、ステレオです。
標準ドライバで動作します。

本プログラムは、[tinyusb uac2_headset](https://github.com/hathach/tinyusb/tree/0.20.0/examples/device/uac2_headset)をベースにしています。


## 使い方
Raspberry Pi Picoに本プログラムを書き込みPCに接続すると、ステレオスピーカーとステレオマイクとして認識されます。デバイス名はpico_usb_audio_loopbackです。  
出力先をpico_usb_audio_loopbackスピーカーび設定した音声のみ、pico_usb_audio_loopbackマイクから出力されます。

## 動作確認端末
Windows11で動作確認しています。

## ビルド方法
### vscodeの拡張機能を使う場合
```
git clone https://github.com/BambooMaster/pico_usb_audio_loopback.git
cd pico_usb_audio_loopback
git submodule update --init
```
を実行した後、vscodeの拡張機能(Raspberry Pi Pico)でインポートし、ビルドしてください。

### vscodeの拡張機能を使わない場合
```
git clone https://github.com/BambooMaster/pico_usb_audio_loopback.git
cd pico_usb_audio_loopback
git submodule update --init
mkdir build && cd build
cmake .. && make -j4
```
