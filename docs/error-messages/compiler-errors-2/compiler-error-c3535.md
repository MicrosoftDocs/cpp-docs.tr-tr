---
title: Derleyici hatası C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: a4bda0825e8b71eb49fe9691755d8e42fd059c06
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510100"
---
# <a name="compiler-error-c3535"></a>Derleyici hatası C3535

' type1 ' için ' type2 ' öğesinden tür çıkarılamıyor

Anahtar sözcüğü tarafından tanımlanan değişkenin türü, **`auto`** başlatma ifadesinin türünden çıkarsanamaz. Örneğin, başlatma ifadesi bir tür olmayan olarak değerlendirilirse bu hata oluşur **`void`** .

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesinin türünün olmadığından emin olun **`void`** .

1. Bildirimin temel bir tür işaretçisi olmadığından emin olun. Daha fazla bilgi için bkz. [temel türler](../../cpp/fundamental-types-cpp.md).

1. Bildirimin bir tür işaretçisi olduğundan, başlatma ifadesinin bir işaretçi türü olduğundan emin olun.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, C3535 verir, çünkü başlatma ifadesi olarak değerlendirilir **`void`** .

```cpp
// C3535a.cpp
// Compile with /Zc:auto
void f(){}
int main()
{
   auto x = f();   //C3535
   return 0;
}
```

Aşağıdaki örnek, C3535 verir, çünkü deyim bir `x` çıkarılmış türe işaretçi olarak değişken bildirir, ancak Başlatıcı ifadesinin türü Double olur. Sonuç olarak, derleyici değişkenin türünü çıkarılamıyor.

```cpp
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

Aşağıdaki örnek, C3535 verir, çünkü değişken `p` çıkarılan bir türe işaretçi bildiriyor, ancak başlatma ifadesi bir işaretçi türü değil.

```cpp
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)<br/>
[Temel türler](../../cpp/fundamental-types-cpp.md)
