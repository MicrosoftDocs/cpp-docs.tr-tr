---
description: 'Daha fazla bilgi edinin: değişken bağımsız değişken listeleri (...) (C++/CLı)'
title: Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
ms.openlocfilehash: fec05a2ce397a0991a4bfd0a5aeb6a8b16d986ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176853"
---
# <a name="variable-argument-lists--ccli"></a>Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)

Bu örnek, `...` değişken sayıda bağımsız değişken içeren işlevleri uygulamak Için C++/CLI ' da söz dizimini nasıl kullanabileceğinizi gösterir.

> [!NOTE]
> Bu konu C++/CLIILE ilgilidir. ISO standart C++ ' ın kullanımı hakkında bilgi için `...` , bkz. [üç nokta ve değişen bağımsız şablonlar](../cpp/ellipses-and-variadic-templates.md) ve üç nokta ve [sonek ifadelerinde](../cpp/postfix-expressions.md)varsayılan bağımsız değişkenler.

Tarafından kullanılan parametre, `...` parametre listesindeki son parametre olmalıdır.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// mcppv2_paramarray.cpp
// compile with: /clr
using namespace System;
double average( ... array<Int32>^ arr ) {
   int i = arr->GetLength(0);
   double answer = 0.0;

   for (int j = 0 ; j < i ; j++)
      answer += arr[j];

   return answer / i;
}

int main() {
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));
}
```

```Output
3
```

## <a name="code-example"></a>Kod Örneği

Aşağıdaki örnek, C# ' den nasıl çağrılacağını, değişken sayıda bağımsız değişken alan bir Visual C++ işlevi gösterir.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

İşlev, `f` C# veya Visual Basic (örneğin, değişken sayıda bağımsız değişken alan bir işlev gibi) çağrılabilir.

C# ' de, bir parametreye geçirilen bir bağımsız değişken, `ParamArray` değişken sayıda bağımsız değişken tarafından çağrılabilir. Aşağıdaki kod örneği C# ' de bulunur.

```csharp
// mcppv2_paramarray3.cs
// compile with: /r:mcppv2_paramarray2.dll
// a C# program

public class X {
   public static void Main() {
      // Visual C# will generate a String array to match the
      // ParamArray attribute
      C myc = new C();
      myc.f("hello", "there", "world");
   }
}
```

`f`Visual C++ ' de yapılan bir çağrı, başlatılmış bir diziyi veya değişken uzunluklu bir diziyi geçirebilir.

```cpp
// mcpp_paramarray4.cpp
// compile with: /clr
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};

int main() {
   C ^ myc = gcnew C();
   myc->f("hello", "world", "!!!");
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Diziler](arrays-cpp-component-extensions.md)
