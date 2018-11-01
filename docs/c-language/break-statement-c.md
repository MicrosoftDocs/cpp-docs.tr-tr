---
title: break Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- break
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
ms.openlocfilehash: 54ece86d629fdaff0113c6f4cebaed7d1b46bb5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646985"
---
# <a name="break-statement-c"></a>break Deyimi (C)

`break` deyimi, göründüğü en yakın kapsayan `do`, `for`, `switch` veya `while` deyiminin yürütülmesini sonlandırır. Denetim, sonlandırılmış deyimi takip eden deyime geçer.

## <a name="syntax"></a>Sözdizimi

*atlama-deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**BREAK;**

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