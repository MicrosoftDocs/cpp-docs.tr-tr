---
title: "Satır içi derleme avantajları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 60b8d458212cd2175f2460c1382ed7f8c2c269bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="advantages-of-inline-assembly"></a>Satır İçi Derleme Avantajları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. C veya C++ deyimleri ile satır içi derleme kodunda karma çünkü sıkıcı veya C veya C++ olanaksız görevler gerçekleştirebilirsiniz.  
  
 Satır içi derleme kullanımları şunlardır:  
  
-   Assembly dili işlevler yazma.  
  
-   Nokta iyileştirme hızı kritik bölümler kod.  
  
-   Doğrudan donanım erişimi için cihaz sürücüleri yapılıyor.  
  
-   "Çıplak" çağrıları için giriş ve bitiş kodu yazmada.  
  
 Satır içi derleme özel amaçlı aracıdır. Farklı makineler uygulamaya bağlantı noktası planlıyorsanız, ayrı bir modül makine özgü kodu yerleştirmek istersiniz. Satır içi derleyicisi tüm Microsoft makro derleyici 's (MASM) desteklemediğinden makrosu ve veri yönergeleri bulduğunuz, daha kullanışlı MASM böyle modülleri için kullanılacak.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)