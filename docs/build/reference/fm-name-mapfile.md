---
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
ms.openlocfilehash: eebb1bc0c553dba1934aea75e2e63edc0f222fff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292412"
---
# <a name="fm-name-mapfile"></a>/Fm (Eşlem Dosyasını Adlandır)

Karşılık gelen bir .exe dosyası veya DLL göründükleri sırayla kesimlerin listesini içeren bir eşlem dosyası üretmek için söyler.

## <a name="syntax"></a>Sözdizimi

```
/Fmpathname
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir eşlem dosyası ile ilgili C veya C++ kaynak dosyasının temel adı verilen bir. Uzantı EŞLEYİN.

Belirtme **/Fm** sizin belirlemiş olsaydık gibi aynı etkiye sahip [Map (eşlem dosyası oluştur)](map-generate-mapfile.md) bağlayıcı seçeneği.

Belirtirseniz [/c (derleme olmadan bağlamayı)](c-compile-without-linking.md) bağlama, gizlemek için **/Fm** hiçbir etkisi olmaz.

Derleyici bir alt çizgi değişken adlarına eklediğinden bir eşlem içindeki genel simgeler, genellikle bir veya daha fazla önde gelen altçizgilere sahip. Mapfile içinde görünen birçok genel simgeler, derleyici ve standart kitaplıkları tarafından dahili olarak kullanılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
