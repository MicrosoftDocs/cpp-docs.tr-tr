---
title: "Önemli hata C1094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1094
dev_langs: C++
helpviewer_keywords: C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 032eee2edf1570e46359d22379843157c6889b4b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1094"></a>Önemli hata C1094
'-Zmval1': önceden derlenmiş üst bilgi oluşturmak için kullanılan değeri ile komut satırı seçeneği tutarsız ('-Zmval2')  
  
 İçin geçirilen değer [/Yc](../../build/reference/yc-create-precompiled-header-file.md) geçirilir aynı değeri olmalıdır [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm** değerleri kullanın ya da aynı önceden derlenmiş oluşturan tüm derlemelerde aynı olmalıdır Üstbilgi dosyası).  
  
 Aşağıdaki örnek C1094 oluşturur:  
  
```  
// C1094.h  
int func1();  
```  
  
 Ardından,  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 Ardından,  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```