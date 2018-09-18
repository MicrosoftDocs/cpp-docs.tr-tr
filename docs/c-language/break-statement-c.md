---
title: Statement (C) kesme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- break
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 008f45375a85a2fc62604885b850f21116c85137
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080382"
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