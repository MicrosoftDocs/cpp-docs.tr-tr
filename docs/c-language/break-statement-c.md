---
title: break Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- break
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
ms.openlocfilehash: 5322f8cb5218882d891e2cd66704f9dbfd1bc149
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90683474"
---
# <a name="break-statement-c"></a>break Deyimi (C)

**`break`** İfadesi, göründüğü en yakın kapsayan **`do`** , **`for`** , **`switch`** , ya da **`while`** deyimin yürütmesini sonlandırır. Denetim, sonlandırılmış deyimi takip eden deyime geçer.

## <a name="syntax"></a>Syntax

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sonundan**

**`break`** Deyimleri, bir deyimindeki belirli bir durumu işlemeyi sonlandırmak için sık kullanılır **`switch`** . Kapsayan yinelemeli veya **`switch`** deyimin olmaması bir hata oluşturur.

İç içe geçmiş deyimler içinde, **`break`** deyimi yalnızca **`do`** **`for`** **`switch`** **`while`** hemen kendisini kapsayan,, veya deyimini sonlandırır. Bir **`return`** veya **`goto`** ifadesini, iç içe geçmiş yapının başka bir yerinde aktarmak için kullanabilirsiniz.

Bu örnek, **`break`** ifadesini göstermektedir:

```C
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

## <a name="see-also"></a>Ayrıca bkz.

[Break ekstresi](../cpp/break-statement-cpp.md)
