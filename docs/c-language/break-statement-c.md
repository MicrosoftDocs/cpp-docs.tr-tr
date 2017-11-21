---
title: Statement (C) sonu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: break
dev_langs: C++
helpviewer_keywords: break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a180c88fc71e4786e8512bc26421825132611ed4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="break-statement-c"></a>break Deyimi (C)
`break` deyimi, göründüğü en yakın kapsayan `do`, `for`, `switch` veya `while` deyiminin yürütülmesini sonlandırır. Denetim, sonlandırılmış deyimi takip eden deyime geçer.  
  
## <a name="syntax"></a>Sözdizimi  
 *atlama deyimi*:  
 `break;`  
  
 `break` deyimi, bir `switch` deyimi içinde belirli bir durumun işlenmesini sonlandırmak için sıkça kullanılır. Yinelemeli bir kapsayan veya `switch` deyimi olmaması bir hata oluşturur.  
  
 İç içe geçmiş deyimler içinde, `break` deyimi yalnızca hemen kendisini kapsayan `do`, `for`, `switch` veya `while` deyimini sonlandırır. Denetimi iç içe geçmiş yapının dışına aktarmak için bir `return` veya `goto` deyimini kullanabilirsiniz.  
  
 Bu örnekte, `break` deyimi gösterilmektedir:  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../cpp/break-statement-cpp.md)