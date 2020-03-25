---
title: Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
ms.openlocfilehash: dfe40d20fc8bb795b0e530b3288b1c2101bc55ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171885"
---
# <a name="variable-argument-lists--ccli"></a>Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)

Bu örnek, değişken sayıda bağımsız değişken içeren işlevleri uygulamak için C++/clı içinde `...` sözdizimini nasıl kullanabileceğinizi gösterir.

> [!NOTE]
> Bu konu,/Cliile C++ilgilidir. ISO standardında C++`...` kullanma hakkında daha fazla bilgi için, bkz. [üç nokta ve değişen bağımsız şablonlar](../cpp/ellipses-and-variadic-templates.md) ve üç nokta ve [sonek ifadelerinde](../cpp/postfix-expressions.md)varsayılan bağımsız değişkenler.

`...` kullanan parametre, parametre listesindeki son parametre olmalıdır.

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

Aşağıdaki örnek, değişken sayıda bağımsız değişken alan C# bir görsel C++ işlevden nasıl çağrılacağını gösterir.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

İşlev `f`, örneğin, değişken sayıda C# bağımsız değişken alan bir işlev gibi, veya Visual Basic çağrılabilir.

' C#De, bir `ParamArray` parametresine geçirilen bir bağımsız değişken, değişken sayıda bağımsız değişken tarafından çağrılabilir. Aşağıdaki kod örneği içinde C#bulunur.

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

Visual C++ 'teki `f` çağrısı, başlatılmış bir diziyi veya değişken uzunluklu bir diziyi geçirebilir.

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
