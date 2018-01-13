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
ms.workload: cplusplus
ms.openlocfilehash: 648ab54d23e22d6c6aae3022593440cb892c1ea9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [break Deyimi](../cpp/break-statement-cpp.md)