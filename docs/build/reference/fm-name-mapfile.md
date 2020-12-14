---
description: Daha fazla bilgi edinin:/FM (mapfile adı)
title: /Fm (Eşlem Dosyasını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: 5c86a18ae9880a499997bcac2d8411859753d858
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200487"
---
# <a name="fm-name-mapfile"></a>/Fm (Eşlem Dosyasını Adlandır)

Bağlayıcının, ilgili. exe dosyasında veya dll 'de göründükleri sırada segmentlerin bir listesini içeren bir eşlem dosyası oluşturmasını söyler.

## <a name="syntax"></a>Syntax

```
/Fmpathname
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, eşlem dosyası ile birlikte karşılık gelen C veya C++ kaynak dosyasının temel adı verilir. MAP uzantısı.

**/FM** belirtildiğinde, [/Map (bir mapfile üret)](map-generate-mapfile.md) bağlayıcı seçeneğini belirtmediğimizden aynı etkiye sahip olur.

Bağlamayı gizlemek için [/c (bağlama olmadan Derle)](c-compile-without-linking.md) belirtirseniz, **/FM** hiçbir etkiye sahip değildir.

Bir eşlem dosyası içindeki genel semboller genellikle bir veya daha fazla önde gelen alt çizgi içerebilir, çünkü derleyici değişken adlarına öncü bir alt çizgi ekliyor. Eşlem dosyası içinde görüntülenen birçok genel sembol derleyici ve standart kitaplıklar tarafından dahili olarak kullanılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol adını belirtme](specifying-the-pathname.md)
