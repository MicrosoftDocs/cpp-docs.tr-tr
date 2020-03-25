---
title: Derleyici Uyarısı (düzey 4) C4127
ms.date: 10/16/2019
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 9d4397c11c4d2f0f9013c7df914cbc4be9fd4e9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198490"
---
# <a name="compiler-warning-level-4-c4127"></a>Derleyici Uyarısı (düzey 4) C4127

> Koşullu ifade sabit

## <a name="remarks"></a>Açıklamalar

**IF** deyiminin veya **while** döngüsünün denetim ifadesi bir sabit olarak değerlendirilir. Visual Studio 2015 güncelleştirme 3 ' ten başlayarak, ortak bir dizi kullanımı nedeniyle, 1 veya **true** gibi önemsiz sabitler, bir ifadede bir işlemin sonucu olmadıkları sürece uyarıyı tetiklemez.

Döngü ortasında çıkış yaptığından **while** döngüsünün denetim ifadesi bir sabit ise **while** döngüsünü bir **for** döngüsü ile değiştirmeyi göz önünde bulundurun. Bir **for** döngüsünün başlatma, sonlandırma testi ve döngü artışını atlayabilirsiniz, bu da döngünün `while(1)`gibi sonsuz olmasına neden olur ve **for** ifadesinin gövdesinden döngüden çıkabilirsiniz.

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
