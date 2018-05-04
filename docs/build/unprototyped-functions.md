---
title: Prototipi oluşturulmamış İşlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df159942832479807b2dfe2679e709292ff3f44b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unprototyped-functions"></a>Prototipi Oluşturulmamış İşlevler
Tam örneklenmemiş işlevler için çağıran tamsayı değerleri tamsayı ve kayan nokta değerlerini çift duyarlıklı olarak geçer. Aranan değeri tamsayı kasalar bekliyor durumda yalnızca kayan nokta değerleri için float değeri tamsayı kaydını ve kayan nokta kaydı içerir.  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)