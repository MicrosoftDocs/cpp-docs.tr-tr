---
title: Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
ms.openlocfilehash: 8ea4d71bf9a22fc96c794a92ba43bed6548cf5d1
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032310"
---
# <a name="variable-argument-lists--ccli"></a>Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)

Bu örnek, c++/CLI'de değişken sayıda bağımsız değişkene sahip işlevleri uygulamak için `...` sözdizimini nasıl kullanabileceğinizi gösterir.

> [!NOTE]
> Bu konu C++/CLI ile ilgilidir. ISO Standart `...` C++'da kullanma hakkında bilgi için, [Postfix ifadelerinde](../cpp/postfix-expressions.md) [Elipsve variadik şablonlar](../cpp/ellipses-and-variadic-templates.md) ve Elipsler ve varsayılan bağımsız değişkenlere bakın.

Kullanan `...` parametre, parametre listesindeki son parametre olmalıdır.

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

Aşağıdaki örnek, değişken sayıda bağımsız değişken alan Bir Görsel C++ işlevi c# dan nasıl çağrılmayı gösterir.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

İşlev `f` C# veya Visual Basic'ten çağrılabilir, örneğin, değişken sayıda bağımsız değişken algılayabilen bir işlevmiş gibi.

C#'da, parametreye geçirilen `ParamArray` bir bağımsız değişken değişken sayıda bağımsız değişken tarafından çağrılabilir. Aşağıdaki kod örneği C#'dadır.

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

Visual `f` C++'da yapılan bir çağrı, başharfe biçilmiş bir diziyi veya değişken uzunluktaki bir diziyi geçirebilir.

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
