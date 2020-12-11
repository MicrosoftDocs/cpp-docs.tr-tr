---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3536'
title: Derleyici hatası C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: 62bd8bb75adfbf0e21f150f4240bb5f4011f6382
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112511"
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

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)
