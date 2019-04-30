---
title: Derleyici Uyarısı (düzey 4) C4127
ms.date: 09/13/2018
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 7f1e23d15d8daa126987278611cb5a85a5a36fc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401322"
---
# <a name="compiler-warning-level-4-c4127"></a>Derleyici Uyarısı (düzey 4) C4127

> Koşullu ifade sabit

## <a name="remarks"></a>Açıklamalar

Denetim ifadesi, bir **varsa** deyimi veya **sırada** döngü için bir sabit olarak değerlendirilir. Visual Studio 2015 güncelleştirme 3, 1 gibi Önemsiz sabitleri başlayarak, yaygın kullanılan deyimsel kullanım nedeniyle veya **true** bir ifadede bir işlemin sonucunu olmadıkları sürece uyarı tetiklemez.

Varsa, Denetim ifadesi bir **sırada** döngüsü, bir sabit ortadaki döngüden çıkılıp çünkü, değiştirmeyi göz önüne alın **sırada** ile döngü bir **için** döngü. Başlatma, sonlandırma testi atlamak ve döngü gelişiminde bir **için** olması gibi sonsuz bir döngüye neden oluyor döngüsü `while(1)`, ve gövdesinden döngüden çıkabilirsiniz **için** deyimi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4127 oluşturulur ve nasıl kullanılacağını gösterir iki yolu gösterir. bir uyarıyı önlemek üzere döngü için:

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```