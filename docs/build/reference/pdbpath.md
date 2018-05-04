---
title: -PDBPATH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 274c4a3742d99b1e4702ed332206b78dacebccbd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [/PDBALTPATH (Diğer PDB Yolunu Kullan)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)