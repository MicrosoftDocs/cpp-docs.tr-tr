---
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
ms.openlocfilehash: f0e770425f8068b15522f405ffdcf7cf52999fe0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820146"
---
# <a name="merge-combine-sections"></a>/MERGE (Bölümleri Birleştir)

```
/MERGE:from=to
```

## <a name="remarks"></a>Açıklamalar

İlk bölüm/Merge seçeneği bir araya getirir (*gelen*) ikinci bölümüyle (*için*), sonuç bölümün adlandırma *için*. Örneğin: `/merge:.rdata=.text`

İkinci bölüm mevcut değilse, bağlantı bölümü yeniden adlandırır *gelen* olarak *için*.

/ Merge seçeneği vxd oluşturup, derleyicinin ürettiği bölüm adları geçersiz kılma için kullanışlıdır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **birleştirme bölümleri** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
