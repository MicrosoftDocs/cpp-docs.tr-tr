---
description: 'Daha fazla bilgi edinin: nasıl yapılır: açıkça paketleme Isteği'
title: 'Nasıl yapılır: Açık Şekilde İstek Paketleme'
ms.date: 11/04/2016
helpviewer_keywords:
- boxing, explicitly requesting
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
ms.openlocfilehash: ebfbae62e5dc35f487974b4bc0e0c3115074a0ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278642"
---
# <a name="how-to-explicitly-request-boxing"></a>Nasıl yapılır: Açık Şekilde İstek Paketleme

Türünde bir değişkene bir değişken atayarak, kutulamayı açıkça isteyebilirsiniz `Object` .

## <a name="example"></a>Örnek

```cpp
// vcmcppv2_explicit_boxing3.cpp
// compile with: /clr
using namespace System;

void f(int i) {
   Console::WriteLine("f(int i)");
}

void f(Object ^o) {
   Console::WriteLine("f(Object^ o)");
}

int main() {
   int i = 5;
   Object ^ O = i;   // forces i to be boxed
   f(i);
   f(O);
   f( (Object^)i );  // boxes i
}
```

```Output
f(int i)
f(Object^ o)
f(Object^ o)
```

## <a name="see-also"></a>Ayrıca bkz.

[Kutulama](../extensions/boxing-cpp-component-extensions.md)
