---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3535'
title: Derleyici hatası C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: ba5019d623fe6f390051084894e13235c6503cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315354"
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
