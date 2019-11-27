---
title: İşlenilmeyen C++ özel durumları
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
ms.openlocfilehash: cd5ce722c5159041ba8fb0a4a41b942a1bd4614f
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246061"
---
# <a name="unhandled-c-exceptions"></a>İşlenilmeyen C++ özel durumları

Geçerli özel durum için eşleşen bir işleyici (veya üç nokta **catch** işleyicisi) bulunamazsa, önceden tanımlı `terminate` çalışma zamanı işlevi çağrılır. (Ayrıca, İşleyicileriniz herhangi birinde `terminate` açıkça çağırabilirsiniz.) `terminate` varsayılan eylemi `abort`çağırmaz. `terminate`'in uygulamadan çıkmadan önce programınızda başka bir işlevi çağırmasını isterseniz, tek bağımsız değişkeni olarak çağrılacak işlevin adıyla birlikte `set_terminate`'i çağırın. Programınızın herhangi bir noktasında `set_terminate`'i çağırabilirsiniz. `terminate` yordamı her zaman `set_terminate`için bağımsız değişken olarak verilen son işlevi çağırır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `char *` özel durumu oluşturur, `char *` türündeki özel durumları yakalayacağı belirtilen bir işleyici içermez. `set_terminate` çağrısı, `terminate`'e `term_func` çağırmasını bildirir.

```cpp
// exceptions_Unhandled_Exceptions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
void term_func() {
   cout << "term_func was called by terminate." << endl;
   exit( -1 );
}
int main() {
   try
   {
      set_terminate( term_func );
      throw "Out of memory!"; // No catch handler for this exception
   }
   catch( int )
   {
      cout << "Integer exception raised." << endl;
   }
   return 0;
}
```

## <a name="output"></a>Çıktı

```Output
term_func was called by terminate.
```

`term_func` işlevi, ideal olarak `exit` çağrısıyla programı veya geçerli iş parçacığını sonlandırmalıdır. Sonlandırmazsa ve bunun yerine arayanına dönerse, `abort` çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](../cpp/errors-and-exception-handling-modern-cpp.md)