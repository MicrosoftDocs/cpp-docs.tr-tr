---
description: Daha fazla bilgi edinin:/MERGE (bölümleri Birleştir)
title: /MERGE (Bölümleri Birleştir)
ms.date: 11/04/2016
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
ms.openlocfilehash: 579e5432facd6deb8d2b26b997d9b61f167d2b3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199109"
---
# <a name="merge-combine-sections"></a>/MERGE (Bölümleri Birleştir)

```
/MERGE:from=to
```

## <a name="remarks"></a>Açıklamalar

/MERGE seçeneği, ilk bölümü (*öğesinden**) ikinci* bölümle birleştirir, sonuç bölümünü *olarak* adlandırın. Örneğin, `/merge:.rdata=.text`.

İkinci bölüm yoksa, *bağlantı bölümünü olarak* *olarak yeniden adlandırır.*

/MERGE seçeneği, VxDs oluşturmak ve derleyicinin ürettiği bölüm adlarını geçersiz kılmak için yararlıdır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Birleştirme bölümleri** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
