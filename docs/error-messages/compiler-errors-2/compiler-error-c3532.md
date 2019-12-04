---
title: Derleyici hatası C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 2ef5eb3c2bedd9defbd0b80e6d8c5c8912fcf16d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761939"
---
# <a name="compiler-error-c3532"></a>Derleyici hatası C3532

' Type ': Hatalı ' Auto ' kullanımı

Belirtilen tür `auto` anahtar sözcüğüyle bildirilemez. Örneğin, bir dizi veya yöntem dönüş türü bildirmek için `auto` anahtar sözcüğünü kullanamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesinin geçerli bir tür aldığından emin olun.

1. Bir dizi veya yöntem dönüş türü bildirdiğinizden emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `auto` anahtar sözcüğü bir yöntem dönüş türü bildiremediği için C3532 verir.

```cpp
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, `auto` anahtar sözcüğü bir dizi bildiremediği için C3532 verir.

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
