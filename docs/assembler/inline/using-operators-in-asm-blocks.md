---
title: "__Asm bloklarında işleçler kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27f01f38e25aac7a7418f24af24e2a58b2ec232b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-operators-in-asm-blocks"></a>__asm Bloklarında İşleçler Kullanma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bir `__asm` blok kullanamaz C veya C++ belirli işleçleri gibi  **<<**  işleci. Ancak, işleçler paylaşılan MASM, C ile gibi \* işleci, assembly dili işletmenler olarak yorumlanır. Örneğin, dışında bir `__asm` engellemek, köşeli parantezleri (**[]**) C dizi öğesi boyutunu otomatik olarak ölçeklendirir dizi indisi kapsayan olarak yorumlanır. İçinde bir `__asm` bloğu, herhangi bir veri nesnesi veya etiket (yalnızca bir dizi) ölçeklendirilmemiş bayt uzaklığı verir MASM dizin işleci olarak görünür. Aşağıdaki kod fark gösterir:  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 İlk referansı `array` ölçeklenmez, ancak saniyedir. Kullanabileceğiniz Not **türü** ölçeklemeyi elde etmek için işlecini temel üzerinde sabiti. Örneğin, aşağıdaki deyimleri eşdeğerdir:  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)