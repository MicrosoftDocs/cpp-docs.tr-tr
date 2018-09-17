---
title: -HEAP (öbek boyutunu Ayarla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
dev_langs:
- C++
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f853b46c9a4cc2ec8f396be2b2f8355270ccf95
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702701"
---
# <a name="heap-set-heap-size"></a>/HEAP (Öbek Boyutunu Ayarla)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

/HEAP seçeneği öbek boyutunu bayt cinsinden ayarlar. Bu seçenek yalnızca bir .exe dosyası oluşturulurken kullanılır.

*Rezerve* bağımsız değişkeni sanal bellekte toplam yığın ayırma belirtir. Varsayılan öbek boyutu 1 MB'dir. Bağlayıcı, belirtilen değeri en yakın 4 bayt yuvarlar.

İsteğe bağlı `commit` bağımsız değişkeni bir kerede ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Daha yüksek bir `commit` değeri kaydeder zaman zaman uygulama daha fazla yığın alanı gerekiyor, ancak bellek gereksinimleri ve büyük olasılıkla başlangıç süresini artırır.

Belirtin *rezerve* ve `commit` değerleri ondalık ya da C dili gösterimi.

Bu işlevi modül tanım dosyası aracılığıyla da kullanılabilir [HEAPSIZE](../../build/reference/heapsize.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **yığın işleme boyutu** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)