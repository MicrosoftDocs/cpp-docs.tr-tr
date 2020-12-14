---
description: Hakkında daha fazla bilgi edinin:/OUT (çıktı dosyası adı)
title: /OUT (Çıktı Dosyası Adı)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
ms.openlocfilehash: 1773b4b2dd340bc105495c1b05211c018548976f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226408"
---
# <a name="out-output-file-name"></a>/OUT (Çıktı Dosyası Adı)

```
/OUT:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Çıktı dosyası için Kullanıcı tarafından belirtilen bir ad. Varsayılan adı değiştirir.

## <a name="remarks"></a>Açıklamalar

/OUT seçeneği, bağlayıcının oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar.

Varsayılan olarak, bağlayıcı dosya adını, belirtilen ilk. obj dosyasının temel adını ve uygun uzantıyı (. exe veya. dll) kullanarak oluşturur.

Bu seçenek, bir. mapfile veya içeri aktarma kitaplığı için varsayılan temel adı. Ayrıntılar için bkz. [mapfile oluşturma](map-generate-mapfile.md) (/Map) ve [/ımplib](implib-name-import-library.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Genel** Özellik sayfasına tıklayın.

1. **Çıkış dosyası** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
