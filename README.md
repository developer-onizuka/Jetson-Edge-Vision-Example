# Jetson Edge Vision Example

## 事前準備

本サンプルコードは Ubuntu 18.04、あるいは JetPack4.4 で動作確認をしています。
以下のソフトウェアをインストールしておいてください。

- CMake 3.x
- OpenCV 3.x
- CUDA 11
- TensorRT 7

また、カメラを利用したサンプルの実行には、1240x720でMotionJPEGフォーマットでキャプチャが可能なUSBカメラが必要です。
カメラが用意できない場合には、下記ビルドの節で説明する動画を入力として使用するモードを利用してください。

## ビルド

以下のコマンドを実行してください。

```
$ mkdir build && cd build
$ cmake ..
$ make
```

カメラを利用しない場合には、app.cc の ENABLE_V4L2_CAMERA を 0 に設定してビルドを行ってください。プログラム中で指定したmp4形式の動画ファイルを読み込んで、推論を実行することができます。

## 実行

セミナー資料に従ってモデルファイルを `trt.engine` という名前で作成し、buildディレクトリ以下に配置した後、以下のコマンドでプログラムを実行してください。

```
$ ./app
```
