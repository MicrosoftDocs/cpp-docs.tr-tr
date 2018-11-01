---
title: Derleyici Hatası C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 91d8e28e053d8ce1b307f9345ab3249386bdf1ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568902"
---
# <a name="compiler-error-c3532"></a>Derleyici Hatası C3532

'type': 'auto' yanlış kullanımı

Belirtilen tür ile bildirilemez `auto` anahtar sözcüğü. Örneğin, kullanamazsınız `auto` anahtar sözcüğü, bir dizi veya bir yöntemi bildirmek için dönüş türü.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesi geçerli bir tür verir emin olun.

1. Bir dizi veya bir yöntemin dönüş türü bildirmeyin emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü C3532 verir `auto` anahtar sözcüğü, bir yöntemin dönüş türü bildiremez.

```
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü C3532 verir `auto` anahtar sözcüğü, bir dizi bildiremez.

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)