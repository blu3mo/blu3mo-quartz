---
title: ffmpegでフレームと動画を双方向変換
---

*ffmpeg*
1fpsの場合

* frame to video
  * [https://ottverse.com/create-video-from-images-using-ffmpeg/](https://ottverse.com/create-video-from-images-using-ffmpeg/)
  * `ffmpeg -framerate 1 -pattern_type glob -i '*.png'  -c:v libx264 -r 1 -pix_fmt yuv420p VIDEONAME.mp4`
  * *glob*が、ファイル名の順番に読めよという指定をしている
    * 注: 桁数を揃えないと正しく順番にならない、2,3,4,5...より100の方が先にくるので、002,003,004,005にしないといけない
* video to frame
  * `ffmpeg -i VIDEONAME.mp4 -vf fps=1 out%d.png`
