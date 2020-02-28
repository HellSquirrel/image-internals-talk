# Материалы к докладу "Картинки как коробки, что же там внутри"

## О чем доклад?

О внутренней структуре популярных форматов изображений (и немножко о видео)

## Слайды

[Слайды на speakerdeck](https://speakerdeck.com/hellsquirrel/kartinki-kak-korobki-chto-zhie-tam-vnutri)

## Полезные штуки (статьи и инструменты)

### О форматах в целом

- [Подробная статья о том что и как :)](https://evilmartians.com/chronicles/images-done-right-web-graphics-good-to-the-last-byte-optimization-techniques)

### PNG

- [Спецификация](https://www.w3.org/TR/2003/REC-PNG-20031110/) (читается легко :)
- [OptiPNG — оптимизатор PNG](http://optipng.sourceforge.net/)

### JPEG

- [Страничка с разнообразными спецификациями](https://www.w3.org/Graphics/JPEG/)
- [Wikipedia JPEG2000](https://en.wikipedia.org/wiki/JPEG_2000)

#### Штуки которые используются в JPEG

- [Y'CbCr color space](https://en.wikipedia.org/wiki/YCbCr)
- [Discrete cosine transform (DCT)](https://en.wikipedia.org/wiki/Discrete_cosine_transform)

### WebP

- [WebP codec](https://github.com/webmproject/libwebp)
- [Оды WebP можно начинать читать отсюда](https://developers.google.com/speed/webp)
- [WebMProject VP8, VP9 кодеки](https://www.webmproject.org/)
- [Техническая статья про детали реализации VP8](https://research.google/pubs/pub37073/)

### AV1

- [Статья про использование AV1](https://evilmartians.com/chronicles/better-web-video-with-av1-codec)
- [Спека AV1](https://aomediacodec.github.io/av1-spec/av1-spec.pdf)
- [Alliance for open media](https://aomedia.org/)

### Tools

- [Squoosh web-интерфейс сжимания всего во все](https://squoosh.app/)
- [Imgproxy](https://imgproxy.net/)
- [mozjpeg](https://github.com/mozilla/mozjpeg)
- [ffmpeg -- video encoding & decoding ](https://www.ffmpeg.org/)
- [optipng](http://optipng.sourceforge.net/)
- [libvips](https://github.com/libvips/libvips)
- [ImageMagick](https://github.com/ImageMagick/ImageMagick/)

## Прикольные команды

Посмотреть что лежит внутри jpeg

```
djpeg -verbose -verbose your-file.jpg > /dev/nul
```

Сделать фрейм AV1 видео (ffmpeg должен быть установлен)

```
ffmpeg -i your-file.jpg -c:v libaom-av1 -crf 48 -b:v 0 -map_metadata -1 -strict experimental your-file-av1.mp4
```

Посмотреть moving vectors (куда двигаются блоки) на видео

```
ffplay -flags2 +export_mvs your-file.mov -vf codecview=pf+bf+bb
```

## Блог марсиан

[Блог марсиан](https://evilmartians.com/chronicles)
