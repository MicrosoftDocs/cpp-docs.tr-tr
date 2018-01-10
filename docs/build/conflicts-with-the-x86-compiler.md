---
title: "X86 çakışıyor derleyici | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b2b9c4cf871e8436a8da34a862d205541e7dc5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="conflicts-with-the-x86-compiler"></a>x86 Derleyicisi ile Çakışma
X86 kullandığınızda 4 bayt yığında otomatik olarak hizalanmaz büyük veri türleri bir uygulama derlemek için derleyicisi. Çünkü derleyici olan bir 4 bayt hizalı yığını, 4 bayttan 64-bit tamsayı, büyük bir şey yapamazsınız otomatik olarak hizalı bir 8 bayt adresine x86 mimarisi.  
  
 Hizalanmamış verilerle iki etkilere sahiptir.  
  
-   Hizalanmamış konumlara erişim hizalanmış konumlarına erişmek için gereken daha uzun sürebilir.  
  
-   Hizalanmamış konumlar birbirine kenetlenmiş işlemler içinde kullanılamaz.  
  
 Daha sıkı hizalama gerekiyorsa kullanın `__declspec(align(N)) on your variable declarations`. Bu, dinamik olarak belirtimleri karşılamak için yığın hizalamak derleyici neden olur. Ancak, yığın çalışma zamanında dinamik olarak ayarlayarak, uygulamanızın yavaş yürütülmesine neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Türler ve depolama](../build/types-and-storage.md)   
 [Hizalama](../cpp/align-cpp.md)