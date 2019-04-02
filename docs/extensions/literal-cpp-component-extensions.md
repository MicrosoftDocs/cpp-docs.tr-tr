---
title: değişmez değer (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
ms.openlocfilehash: dc48f2e14ec9a79a92882c23f584bf03303b03a3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787145"
---
# <a name="literal-ccli-and-ccx"></a>değişmez değer (C + +/ CLI ve C + +/ CX)

Bir değişken (veri üyesi) olarak işaretlenmiş **değişmez değer** içinde bir **/CLR** derleme yerel denk olan bir **statik const** değişkeni.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

## <a name="remarks"></a>Açıklamalar

Bir veri üyesi olarak işaretlenmiş **değişmez değer** bildirildiğinde başlatılmalıdır ve değeri bir sabit integral, enum veya dize türü olmalıdır. Statik const veri üye türü başlatma ifadesinin türünden dönüştürme, bir kullanıcı tanımlı dönüştürme gerektirmemelidir.

Bellek yok, çalışma zamanında sabit değerli alan için ayrılır; Derleyici, değeri yalnızca meta sınıf ekler.

Bir değişken olarak işaretlenmiş **statik const** diğer derleyicileri için meta verilerinde kullanılamaz.

Daha fazla bilgi için [statik](../cpp/storage-classes-cpp.md) ve [const](../cpp/const-cpp.md).

**değişmez değer** bağlama duyarlı bir anahtar sözcüktür. Bkz: [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Bu örnek, gösterir bir **değişmez değer** değişkeni gelir **statik**.

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

Aşağıdaki örnek, değişmez değer meta verilerinde etkisini gösterir:

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Fark için meta verilerindeki `sc` ve `lit`: `modopt` yönergesi uygulanan `sc`, yani yoksayılan diğer derleyiciler tarafından.

```
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)
```

```
.field public static literal int32 lit = int32(0x0000000A)
```

## <a name="example"></a>Örnek

C# dilinde yazılmış aşağıdaki örnek, önceki örnekte oluşturulan meta veri başvuruları ve etkisini gösterir **değişmez değer** ve **statik const** değişkenleri:

```cs
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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)