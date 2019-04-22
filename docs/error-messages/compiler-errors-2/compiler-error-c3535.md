---
title: Derleyici Hatası C3535
ms.date: 11/04/2016
f1_keywords:
- C3535
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
ms.openlocfilehash: e80fa62db9795838980c63e113300a554afabef3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040867"
---
# <a name="compiler-error-c3535"></a>Derleyici Hatası C3535

'type1' öğesinden 'type2' türü çıkarılamıyor

Tarafından bildirilen bir değişken türü `auto` anahtar sözcüğü bir başlatma ifadesinin türünden atanan olamaz. Örneğin, başlatma ifadesi değerlendirilir, bu hata meydana gelir `void`, bir tür değil.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesi türü olmadığından emin olun `void`.

1. Bildiriminin bir temel türü bir işaretçi olmadığından emin olun. Daha fazla bilgi için [temel türler](../../cpp/fundamental-types-cpp.md).

1. Başlatma ifadesi bildirimi bir tür için bir işaretçi ise, işaretçi türünde olduğundan emin olun.

## <a name="example"></a>Örnek

Başlatma ifadenin değerlendirdiği olduğundan aşağıdaki örnekte C3535 verir `void`.

```
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

Deyim değişkeni bildirdiğinden, aşağıdaki örnekte C3535 verir `x` çıkarılan bir türü, ancak Başlatıcı türü için bir işaretçi olarak çift ifadesidir. Sonuç olarak, derleyici değişkenin türü çıkarılamıyor.

```
// C3535b.cpp
// Compile with /Zc:auto
int main()
{
   auto* x = 123.0;   // C3535
   return 0;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü C3535 verir değişkeni `p` çıkarılan bir türü için bir işaretçiyi bildirir, ancak başlatma ifadesi bir işaretçi türü değil.

```
// C3535c.cpp
// Compile with /Zc:auto
class A { };
A x;
auto *p = x;  // C3535
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[Temel Türler](../../cpp/fundamental-types-cpp.md)