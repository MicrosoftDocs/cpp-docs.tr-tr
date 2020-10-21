---
title: değişmez değer (C++/CLı)
description: Literal anahtar sözcüğü, bir derleme zamanı sabiti için Microsoft C++/CLı bağlama duyarlı bir anahtar sözcüktür.
ms.date: 10/20/2020
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.openlocfilehash: 2d71a535252ba51f89407670b474a34b407eaffc
ms.sourcegitcommit: 59b7c18703d1ffd66827db0e2eeece490d3d8789
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2020
ms.locfileid: "92337219"
---
# <a name="literal-ccli"></a>`literal` (C++/CLı)

Derlemede olarak işaretlenen bir değişken (veri üyesi) bir **`literal`** **`/clr`** derleme zamanı sabiti olur. Bu, bir C# değişkeninin yerel eşdeğeridir [`const`](/dotnet/csharp/language-reference/keywords/const) .

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliği için yalnızca Windows Çalışma Zamanı uygulanan bir açıklama yoktur.)

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

## <a name="remarks"></a>Açıklamalar

Olarak işaretlenen bir veri üyesinin, **`literal`** bildirildiği sırada başlatılması gerekir. Değer, sabit bir integral, Enum veya dize türü olmalıdır. Başlatma ifadesinin türünden veri üyesinin türüne dönüştürme için **`literal`** Kullanıcı tanımlı dönüştürme gerekli değildir.

Çalışma zamanında alan için bellek ayrılmamış **`literal`** ; derleyici, değerini yalnızca sınıfının meta verilerine ekler. **`literal`** Değer, derleme zamanı sabiti olarak değerlendirilir. Standart C++ ' da en yakın eşdeğeri **`constexpr`** , ancak bir veri üyesi **`constexpr`** C++/clide olamaz.

Olarak işaretlenen bir değişken, **`literal`** işaretli olandan farklı **`static const`** . Bir **`static const`** veri üyesi diğer derleyicilere meta verilerde kullanılabilir hale getirilmez. Daha fazla bilgi için bkz [`static`](../cpp/storage-classes-cpp.md) [`const`](../cpp/const-cpp.md) . ve.

**`literal`** bağlama duyarlı bir anahtar sözcüktür. Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Örnekler

Bu örnekte bir **`literal`** değişkenin gösterdiği gösterilmektedir **`static`** .

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

Aşağıdaki örnek **`literal`** meta verilerde etkisini gösterir:

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Ve için meta verilerde farklılık olduğunu fark `sc` edin `lit` : `modopt` yönerge öğesine uygulanır `sc` , yani diğer derleyiciler tarafından yoksayılabilir.

```MSIL
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x00000001)
```

```MSIL
.field public static literal int32 lit = int32(0x00000000)
```

C# dilinde yazılan aşağıdaki örnek, önceki örnekte oluşturulan meta verilere başvurur ve **`literal`** ve değişkenlerinin etkisini gösterir **`static const`** :

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

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
