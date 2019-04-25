---
title: /HEAP (Öbek Boyutunu Ayarla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
ms.openlocfilehash: 715eaa358d052d4ae646f38f2e784f0235dffccb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270360"
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

Bu işlevi modül tanım dosyası aracılığıyla da kullanılabilir [HEAPSIZE](heapsize.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **yığın işleme boyutu** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
