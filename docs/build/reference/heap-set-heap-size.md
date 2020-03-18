---
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
ms.openlocfilehash: f155ad56ec1a90479b402e38e7ec7f3e3d80e470
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439530"
---
# <a name="heap-set-heap-size"></a>/HEAP (Öbek Boyutunu Ayarla)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

/HEAP seçeneği, yığının boyutunu bayt cinsinden ayarlar. Bu seçenek yalnızca bir. exe dosyası oluşturulurken kullanılır.

*Reserve* bağımsız değişkeni, sanal bellekteki toplam yığın ayırmayı belirtir. Varsayılan yığın boyutu 1 MB 'tır. Bağlayıcı belirtilen değeri en yakın 4 bayta yuvarlar.

İsteğe bağlı `commit` bağımsız değişkeni, bir seferde ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek, disk belleği dosyasında ayrılan alanın ayrılmasına neden olur. Daha yüksek bir `commit` değeri, uygulamanın daha fazla yığın alanına ihtiyacı olduğunda zaman kazandırır, ancak bellek gereksinimlerini ve muhtemelen başlangıç süresini arttırır.

Decimal veya C-Language gösteriminde *Reserve* ve `commit` değerlerini belirtin.

Bu işlev, [heapsize](heapsize.md)ile bir modül tanım dosyası aracılığıyla da kullanılabilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Sistem** Özellik sayfasına tıklayın.

1. **Yığın yürütmesi boyut** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
