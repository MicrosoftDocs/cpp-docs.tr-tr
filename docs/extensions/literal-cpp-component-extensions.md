---
title: değişmez değerC++(/CLI C++ve/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
ms.openlocfilehash: d567f8270dcb8965ed2f882c9a0c005f295fc619
ms.sourcegitcommit: c4528a7424d35039454f17778baf1b5f98fbbee7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912833"
---
# <a name="literal-ccli-and-ccx"></a>değişmez değerC++(/CLI C++ve/CX)

**/Clr** derlemesinde **sabit değer** olarak işaretlenen bir değişken (veri üyesi), **statik bir const** değişkeninin yerel eşdeğeridir.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliği için yalnızca Windows Çalışma Zamanı uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

## <a name="remarks"></a>Açıklamalar

**Değişmez** değer olarak işaretlenen bir veri üyesi, bildirildiği zaman başlatılmalıdır ve değerin sabit bir integral, sabit listesi veya dize türü olması gerekir. Başlatma ifadesinin türünden statik const veri üyesinin türüne dönüştürme, Kullanıcı tanımlı bir dönüştürme gerektirmemelidir.

Çalışma zamanında sabit değer alanı için bellek ayrılmamış; Derleyici, değerini yalnızca sınıfının meta verilerine ekler.

**Statik const** olarak işaretlenmiş bir değişken, diğer derleyicilere meta verilerde kullanılamaz.

Daha fazla bilgi için bkz. [static](../cpp/storage-classes-cpp.md) ve [const](../cpp/const-cpp.md).

**değişmez değer** , bağlama duyarlı bir anahtar sözcüktür. Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Bu örnek, **sabit** bir değişkenin **statik**olduğunu gösterir.

```cpp
// mcppv2_literal.cpp
// compile with: /clr
ref struct X {
   literal int i = 4;
};

int main() {
   int value = X::i;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek meta verilerde sabit değerin etkisini gösterir:

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

`sc` ve `lit`meta verilerindeki farka dikkat edin: `modopt` yönergesi `sc`uygulanır, yani diğer derleyiciler tarafından yoksayılabilir.

```
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)
```

```
.field public static literal int32 lit = int32(0x0000000A)
```

## <a name="example"></a>Örnek

İçinde C#yazılan aşağıdaki örnek, önceki örnekte oluşturulan meta verilere başvurur ve **değişmez değer** ve **statik const** değişkenlerinin etkisini gösterir:

```csharp
// mcppv2_literal3.cs
// compile with: /reference:mcppv2_literal2.dll
// A C# program
class B {
   public static void Main() {
      // OK
      System.Console.WriteLine(A.lit);
      System.Console.WriteLine(A.sc);

      // C# does not enforce C++ const
      A.sc = 9;
      System.Console.WriteLine(A.sc);

      // C# enforces const for a literal
      A.lit = 9;   // CS0131

      // you can assign a C++ literal variable to a C# const variable
      const int i = A.lit;
      System.Console.WriteLine(i);

      // but you cannot assign a C++ static const variable
      // to a C# const variable
      const int j = A.sc;   // CS0133
      System.Console.WriteLine(j);
   }
}
```

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)