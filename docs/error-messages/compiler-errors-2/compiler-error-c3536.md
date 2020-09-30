---
title: Derleyici hatası C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: 2380a9d42525cfb662fa014b89751d6dc8b9f192
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508249"
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
