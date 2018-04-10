---
title: -PDBPATH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /pdbpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ccbcedbf9cdd376fa7d9bced5c9d49542cee9f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pdbpath"></a>/PDBPATH
```  
/PDBPATH[:VERBOSE] filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Eşleşen .pdb dosyasını bulmak istediğiniz .dll veya .exe dosyasının adı.  
  
 VERBOSE (isteğe bağlı)  
 Rapor, tüm dizinler burada .pdb dosyasını bulmak için girişimde bulunuldu.  
  
## <a name="remarks"></a>Açıklamalar  
 / PDBPATH bilgisayarınızı, varsa, .pdb dosyaları belirtilen dosyaya karşılık gelen hata ayıklayıcı bir .pdb dosyasını aramak ve rapor eder aynı yol boyunca arayacak *filename*.  
  
 Hata ayıklayıcı .pdb dosyasını ayıkladığınız dosyayı farklı bir sürümünü kullanıyor due için nedeni, Visual Studio hata ayıklayıcısı kullanırken bir sorunla karşılaşabilirsiniz.  
  
 / PDBPATH aşağıdaki yolları boyunca .pdb dosyaları arar:  
  
-   Yürütülebilir dosyanın bulunduğu konuma denetleyin.  
  
-   Yürütülebilir dosyada yazılmış PDB konumunu denetleyin. Bu genellikle görüntünün bağlı olduğu anda konumdur.  
  
-   Visual Studio IDE içinde yapılandırılmış arama yol boyunca denetleyin.  
  
-   _NT_ALT_SYMBOL_PATH ve _NT_SYMBOL_PATH yollarında boyunca ortam değişkenleri denetleyin.  
  
-   Windows dizini denetleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN seçenekleri](../../build/reference/dumpbin-options.md)   
 [/ PDBALTPATH (diğer PDB yolunu kullan)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)