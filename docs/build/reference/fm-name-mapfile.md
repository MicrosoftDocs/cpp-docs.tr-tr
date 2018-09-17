---
title: -Fm (eşlem dosyasını Adlandır) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fm
dev_langs:
- C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e69a273d523a78adc2b71652e5f13fb9141d3b1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699915"
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

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)