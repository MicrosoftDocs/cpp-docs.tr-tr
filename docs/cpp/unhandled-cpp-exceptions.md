---
title: İşlenmeyen C++ özel durumlarını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], unhandled exceptions
- catch keyword [C++], handler not found
- exceptions [C++], unhandled
- C++ exception handling, unhandled exceptions
- unhandled exceptions [C++]
ms.assetid: 13f09c53-9254-4407-9db9-14e730e047cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 57d014762ebc5427ccc4b9d26fff75addc883759
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097776"
---
# <a name="unhandled-c-exceptions"></a>İşlenilmeyen C++ Özel Durumları

Eşleşen bir işleyici (ya da üç nokta **catch** işleyicisi) geçerli özel durum için önceden tanımlanmış nebyla nalezena `terminate` çalışma zamanı işlevi çağrılır. (İşleyicilerinizden herhangi birinde `terminate`'i de açıkça çağırabilirsiniz.) Varsayılan `terminate` işlemi, `abort` çağırmaktır. `terminate`'in uygulamadan çıkmadan önce programınızda başka bir işlevi çağırmasını isterseniz, tek bağımsız değişkeni olarak çağrılacak işlevin adıyla birlikte `set_terminate`'i çağırın. Programınızın herhangi bir noktasında `set_terminate`'i çağırabilirsiniz. `terminate` Yordamı her zaman bir bağımsız değişken olarak verilen son işlevi çağırır `set_terminate`.

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

## <a name="output"></a>Çıkış

```Output
term_func was called by terminate.
```

`term_func` işlevi, ideal olarak `exit` çağrısıyla programı veya geçerli iş parçacığını sonlandırmalıdır. Sonlandırmazsa ve bunun yerine arayanına dönerse, `abort` çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)