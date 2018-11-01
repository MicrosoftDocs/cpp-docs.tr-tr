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
ms.openlocfilehash: 49a3d20aee54b06bae2670be139d748fd2aaca6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469864"
---
# <a name="fm-name-mapfile"></a>/Fm (Eşlem Dosyasını Adlandır)

Karşılık gelen bir .exe dosyası veya DLL göründükleri sırayla kesimlerin listesini içeren bir eşlem dosyası üretmek için söyler.

## <a name="syntax"></a>Sözdizimi

```
/Fmpathname
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir eşlem dosyası ile ilgili C veya C++ kaynak dosyasının temel adı verilen bir. Uzantı EŞLEYİN.

Belirtme **/Fm** sizin belirlemiş olsaydık gibi aynı etkiye sahip [Map (eşlem dosyası oluştur)](../../build/reference/map-generate-mapfile.md) bağlayıcı seçeneği.

Belirtirseniz [/c (derleme olmadan bağlamayı)](../../build/reference/c-compile-without-linking.md) bağlama, gizlemek için **/Fm** hiçbir etkisi olmaz.

Derleyici bir alt çizgi değişken adlarına eklediğinden bir eşlem içindeki genel simgeler, genellikle bir veya daha fazla önde gelen altçizgilere sahip. Mapfile içinde görünen birçok genel simgeler, derleyici ve standart kitaplıkları tarafından dahili olarak kullanılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)