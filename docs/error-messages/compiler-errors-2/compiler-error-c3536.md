---
title: Derleyici hatası C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: a140847b642ac2437b67aa957328c3b8fbfc592d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761575"
---
# <a name="compiler-error-c3536"></a>Derleyici hatası C3536

' symbol ': başlatılmadan önce kullanılamaz

Belirtilen sembol başlatılmadan önce kullanılamaz. Pratikte bu, değişken kendisini başlatmak için kullanılamayan anlamına gelir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Bir değişkeni kendi kendine başlatmayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, her değişken kendisiyle başlatıldığı için C3536 verir.

```cpp
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
