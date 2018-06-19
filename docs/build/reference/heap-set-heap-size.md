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
ms.openlocfilehash: 7b968b3c8e9063eea897c70d4ae2a62a9a232d6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374563"
---
# <a name="heap-set-heap-size"></a>/HEAP (Öbek Boyutunu Ayarla)
```  
/HEAP:reserve[,commit]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /HEAP seçeneği öbek boyutunu bayt cinsinden ayarlar. Bu seçenek yalnızca bir .exe dosyası oluşturulurken kullanılır.  
  
 *Yedek* bağımsız değişkeni, sanal bellek toplam yığın ayırma belirtir. Varsayılan yığın boyutu 1 MB'tır. Bağlayıcı yakın 4 bayt belirtilen değere yukarı yuvarlar.  
  
 İsteğe bağlı `commit` bağımsız değişkeni aynı anda ayırmak için fiziksel bellek miktarını belirtir. Kaydedilebilen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Yüksek bir `commit` zaman uygulama daha fazla yığın alanı gerekiyor, ancak bellek gereksinimlerini ve büyük olasılıkla başlangıç zamanını artırır zaman kaydeder.  
  
 Belirtin *yedek* ve `commit` değerleri ondalık veya dil C gösterimi.  
  
 Bu işlev ile modül tanım dosyası aracılığıyla da kullanılabilir [HEAPSIZE](../../build/reference/heapsize.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **sistem** özellik sayfası.  
  
4.  Değiştirme **yığın boyutu yürütme** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)