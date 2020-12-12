---
description: :/HEAP hakkında daha fazla bilgi edinin (yığın boyutunu ayarla)
title: /HEAP (Öbek Boyutunu Ayarla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- VC.Project.VCLinkerTool.HeapReserveSize
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
ms.openlocfilehash: 9831180925d5d669c799982d021d75ea31a2dae5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191673"
---
# <a name="heap-set-heap-size"></a>/HEAP (Öbek Boyutunu Ayarla)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

/HEAP seçeneği, yığının boyutunu bayt cinsinden ayarlar. Bu seçenek yalnızca bir. exe dosyası oluşturulurken kullanılır.

*Reserve* bağımsız değişkeni, sanal bellekteki toplam yığın ayırmayı belirtir. Varsayılan yığın boyutu 1 MB 'tır. Bağlayıcı belirtilen değeri en yakın 4 bayta yuvarlar.

İsteğe bağlı `commit` bağımsız değişken, bir seferde ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek, disk belleği dosyasında ayrılan alanın ayrılmasına neden olur. `commit`Uygulamanın daha fazla yığın alanına ihtiyacı olduğunda daha yüksek bir değer zaman kazandırır, ancak bellek gereksinimlerini ve muhtemelen başlangıç süresini arttırır.

 `commit` Decimal veya C-Language gösteriminde Reserve ve değerler belirtin.

Bu işlev, [heapsize](heapsize.md)ile bir modül tanım dosyası aracılığıyla da kullanılabilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Sistem** Özellik sayfasına tıklayın.

1. **Yığın yürütmesi boyut** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A> . ve.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
