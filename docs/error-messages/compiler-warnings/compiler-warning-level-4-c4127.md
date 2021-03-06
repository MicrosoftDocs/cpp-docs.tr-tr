---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4127'
title: Derleyici Uyarısı (düzey 4) C4127
ms.date: 10/16/2019
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 54c319c6894c0a82c99100c736498466a1c7c135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261898"
---
# <a name="compiler-warning-level-4-c4127"></a>Derleyici Uyarısı (düzey 4) C4127

> Koşullu ifade sabit

## <a name="remarks"></a>Açıklamalar

**`if`** Deyim veya döngünün denetim ifadesi **`while`** bir sabit olarak değerlendirilir. Ortak Ise kullanımı nedeniyle, Visual Studio 2015 güncelleştirme 3 ' ten başlayarak, bir ifadede bir işlemin sonucu olmadıkları sürece, 1 gibi önemsiz sabitler veya **`true`** uyarı tetiklemez.

Döngü **`while`** ortasında çıkış yaptığından döngünün denetim ifadesi bir sabit ise **`while`** döngüyü bir **`for`** döngüyle değiştirmeyi düşünün. Bir döngünün başlatma, sonlandırma testi ve döngü artışını atlayabilirsiniz **`for`** , bu da döngünün yalnızca gibi sonsuz olmasına neden olur `while(1)` ve ifadenin gövdesinden gelen döngüden çıkabilirsiniz **`for`** .

## <a name="example"></a>Örnek

Aşağıdaki örnekte, C4127 'in oluşturulduğu iki yol gösterilmektedir ve uyarıyı önlemek için bir for döngüsünün nasıl kullanılacağı gösterilmektedir:

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

Bu uyarı, koşullu ifadede bir derleme zamanı sabiti kullanıldığında da oluşturulabilir:

```cpp
#include <string>

using namespace std;

template<size_t S, class T>
void MyFunc()
{
   if (sizeof(T) >= S) // C4127. "Consider using 'if constexpr' statement instead"
   {
   }
}

class Foo
{
   int i;
   string s;
};

int main()
{
   Foo f;
   MyFunc<4, Foo>();
}
```
