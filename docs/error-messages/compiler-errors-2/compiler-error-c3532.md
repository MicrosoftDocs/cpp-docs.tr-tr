---
title: Derleyici hatası C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: e2329111e916df9eac99d156bcf58a58e148cb08
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228823"
---
# <a name="compiler-error-c3532"></a>Derleyici hatası C3532

' Type ': Hatalı ' Auto ' kullanımı

Belirtilen tür **`auto`** anahtar sözcüğüyle bildirilemez. Örneğin, **`auto`** bir dizi veya yöntem dönüş türü bildirmek için anahtar sözcüğünü kullanamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesinin geçerli bir tür aldığından emin olun.

1. Bir dizi veya yöntem dönüş türü bildirdiğinizden emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3532 verir çünkü **`auto`** anahtar sözcüğü bir yöntem dönüş türü bildiremez.

```cpp
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3532 verir çünkü **`auto`** anahtar sözcüğü bir dizi bildiremez.

```cpp
// C3532b.cpp
// Compile with /Zc:auto
int main()
{
   int x[5];
   auto a[5];            // C3532
   auto b[1][2];         // C3532
   auto y[5] = x;        // C3532
   auto z[] = {1, 2, 3}; // C3532
   auto w[] = x;         // C3532
   return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
