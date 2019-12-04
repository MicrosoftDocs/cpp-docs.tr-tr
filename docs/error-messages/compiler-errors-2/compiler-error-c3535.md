---
title: Derleyici hatası C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: 6b487c0f94a00ec64e0c2178265c5a8c27544a51
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761562"
---
# <a name="compiler-error-c3535"></a>Derleyici hatası C3535

' type1 ' için ' type2 ' öğesinden tür çıkarılamıyor

`auto` anahtar sözcüğüyle belirtilen değişkenin türü, başlatma ifadesinin türünden çıkarsanamaz. Örneğin, başlatma ifadesi bir tür olmayan `void`değerlendirilirse bu hata oluşur.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesinin türünün `void`olmadığından emin olun.

1. Bildirimin temel bir tür işaretçisi olmadığından emin olun. Daha fazla bilgi için bkz. [temel türler](../../cpp/fundamental-types-cpp.md).

1. Bildirimin bir tür işaretçisi olduğundan, başlatma ifadesinin bir işaretçi türü olduğundan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, başlatma ifadesi `void`olarak değerlendirildiği için C3535 verir.

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

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3535 verir, çünkü deyim çıkarılan bir tür işaretçisi olarak değişken `x` bildiriyor, ancak Başlatıcı ifadesinin türü Double. Sonuç olarak, derleyici değişkenin türünü çıkarılamıyor.

```cpp
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, değişken `p` çıkarılan bir türe işaretçi bildirdiğinden, ancak başlatma ifadesi bir işaretçi türü olmadığı için C3535 verir.

```cpp
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[Temel Türler](../../cpp/fundamental-types-cpp.md)
