---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3532'
title: Derleyici hatası C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 754f69bd3ee24b94be6725864a5e9cd3993d2148
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315315"
---
# <a name="compiler-error-c3532"></a>Derleyici hatası C3532

' Type ': Hatalı ' Auto ' kullanımı

Belirtilen tür **`auto`** anahtar sözcüğüyle bildirilemez. Örneğin, **`auto`** bir dizi veya yöntem dönüş türü bildirmek için anahtar sözcüğünü kullanamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Başlatma ifadesinin geçerli bir tür aldığından emin olun.

1. Bir dizi veya yöntem dönüş türü bildirdiğinizden emin olun.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, C3532 verir çünkü **`auto`** anahtar sözcüğü bir yöntem dönüş türü bildiremez.

```cpp
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

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

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)
