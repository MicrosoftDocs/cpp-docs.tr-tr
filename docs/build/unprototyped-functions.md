---
title: "Prototipi oluşturulmamış İşlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbc9324753f6ec2c9a332af00a00dd85116e1943
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Çağırma kuralı](../build/calling-convention.md)