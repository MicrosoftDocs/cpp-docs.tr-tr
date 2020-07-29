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
ms.openlocfilehash: 48b417c48a3cbb903f3fabaf31b1423e79a1a414
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233593"
---
# <a name="unhandled-c-exceptions"></a>İşlenilmeyen C++ özel durumları

Geçerli özel durum için eşleşen bir işleyici (veya üç nokta **`catch`** işleyicisi) bulunamazsa, önceden tanımlanmış `terminate` çalışma zamanı işlevi çağrılır. (Ayrıca İşleyicileriniz herhangi birinde açıkça çağrı yapabilirsiniz `terminate` .) Varsayılan eylemi `terminate` çağrdır `abort` . `terminate`'in uygulamadan çıkmadan önce programınızda başka bir işlevi çağırmasını isterseniz, tek bağımsız değişkeni olarak çağrılacak işlevin adıyla birlikte `set_terminate`'i çağırın. Programınızın herhangi bir noktasında `set_terminate`'i çağırabilirsiniz. `terminate`Yordamı her zaman bir bağımsız değişken olarak verilen son işlevi çağırır `set_terminate` .

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

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)
