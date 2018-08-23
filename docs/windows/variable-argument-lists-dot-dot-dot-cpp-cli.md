---
title: Değişken bağımsız değişken listeleri (...) (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e58b7ea2d8db0c3d36ad36aaccbf23957c449a77
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590469"
---
# <a name="variable-argument-lists--ccli"></a>Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)

Bu örnek nasıl kullanılacağını göstermektedir `...` değişken sayıda bağımsız değişkenlere sahip işlevler uygulamak için Visual c++ sözdizimi.

> [!NOTE]
> Bu konuda ilgilidir C + +/ CLI. Kullanma hakkında bilgi için `...` ISO Standard C++ içinde bkz [üç nokta ve Variadic şablonları](../cpp/ellipses-and-variadic-templates.md) ve üç nokta ve varsayılan bağımsız değişkenler [sonek ifadeleri](../cpp/postfix-expressions.md).

Kullanan bir parametre `...` parametre listesindeki son parametre olmalıdır.

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

Aşağıdaki örnek, C# ' den, değişken sayıda bağımsız değişken alan bir Visual C++ işlevinin nasıl çağrıldığını gösterir.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

İşlev `f` işlevmiş gibi bir değişken sayıda bağımsız değişken alan bir işlev C# veya Visual Basic gibi çağrılabilir.

C#, geçirilen bir bağımsız değişken bir `ParamArray` parametre bağımsız değişkenin değişken numarası tarafından çağrılabilir. Aşağıdaki kod örneği C# ' dir.

```cs
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

Bir çağrı `f` Visual c++'ta başlatılan diziyi veya değişken uzunluklu diziyi geçirebilir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Diziler](../windows/arrays-cpp-component-extensions.md)