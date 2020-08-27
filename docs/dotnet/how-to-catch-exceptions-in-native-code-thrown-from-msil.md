---
title: "Nasıl yapılır: MSIL'den oluşan yerel kodda catch özel durumları"
description: MSIL 'den oluşan yerel kodda özel durumların nasıl yakalanalınacağını gösteren örnekler.
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: b68a771d27e091f86331703b55bc2eb52dfbb41b
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898585"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Nasıl yapılır: MSIL'den oluşan yerel kodda catch özel durumları

Yerel kodda yerel C++ özel durumunu MSIL 'den yakalayabilirsiniz.  CLR özel durumlarını ve ile yakalayabilirsiniz **`__try`** **`__except`** .

Daha fazla bilgi için bkz. [özel durumlar ve hata işleme Için](../cpp/errors-and-exception-handling-modern-cpp.md) [yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md) ve modern C++ en iyi uygulamaları.

## <a name="example-1"></a>Örnek 1

Aşağıdaki örnek iki işlevi olan bir modül tanımlar, biri yerel özel durum oluşturur ve bir MSIL özel durumu oluşturur.

```cpp
// catch_MSIL_in_native.cpp
// compile with: /clr /c
void Test() {
   throw ("error");
}

void Test2() {
   throw (gcnew System::Exception("error2"));
}
```

## <a name="example-2"></a>Örnek 2

Aşağıdaki örnek, yerel ve MSIL özel durumunu yakalayan bir modül tanımlar.

```cpp
// catch_MSIL_in_native_2.cpp
// compile with: /clr catch_MSIL_in_native.obj
#include <iostream>
using namespace std;
void Test();
void Test2();

void Func() {
   // catch any exception from MSIL
   // should not catch Visual C++ exceptions like this
   // runtime may not destroy the object thrown
   __try {
      Test2();
   }
   __except(1) {
      cout << "caught an exception" << endl;
   }

}

int main() {
   // catch native C++ exception from MSIL
   try {
      Test();
   }
   catch(char * S) {
      cout << S << endl;
   }
   Func();
}
```

```Output
error
caught an exception
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum işleme](../extensions/exception-handling-cpp-component-extensions.md)
