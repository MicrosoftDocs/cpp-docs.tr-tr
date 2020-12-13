---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3293'
title: Derleyici hatası C3293
ms.date: 07/21/2017
f1_keywords:
- C3293
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
ms.openlocfilehash: 5ba4256997eed12d3a380d5f3a4d1876da75fb8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144644"
---
# <a name="compiler-error-c3293"></a>Derleyici hatası C3293

' erişimci ': ' Type ' sınıfının varsayılan özelliğine (Dizin Oluşturucu) erişmek için ' default ' kullanın

Dizinli bir özelliğe yanlış erişildi.  Daha fazla bilgi için bkz. [nasıl yapılır: C++/CLI üzerinde özellikleri kullanma](../../dotnet/how-to-use-properties-in-cpp-cli.md) .

**Visual studio 2017 ve üzeri**: visual Studio 2015 ve önceki sürümlerde derleyici, bazı durumlarda varsayılan bir dizin oluşturucu olarak varsayılan bir özelliği yanlış tanımladı. Bu özelliğe erişmek için "default" tanımlayıcısını kullanarak soruna geçici bir çözüm olabilir. Geçici çözüm, C++ 11 ' de varsayılan anahtar sözcük olarak sunulduktan sonra sorunlu olur. Bu nedenle, Visual Studio 2017 ' de geçici çözümü gerektiren hatalar düzeltildi ve derleyici, bir sınıf için varsayılan özelliğe erişmek üzere "varsayılan" kullanıldığında bir hata oluşturuyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2015 ve önceki sürümlerde C3293 oluşturur.

```cpp
// C3293.cpp
// compile with: /clr /c
using namespace System;
ref class IndexerClass {
public:
   // default indexer
   property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};

int main() {
   IndexerClass ^ ic = gcnew IndexerClass;
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier

   String ^s = "Hello";
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier
   Console::WriteLine(wc2);
}
```
