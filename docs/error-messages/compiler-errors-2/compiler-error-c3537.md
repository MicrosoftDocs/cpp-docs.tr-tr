---
title: Derleyici Hatası C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 50a06180dabfa192292fae7ba1962b6b7455bb89
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024030"
---
# <a name="compiler-error-c3537"></a>Derleyici Hatası C3537

'type': 'auto' içeren bir türe dönüştüremezsiniz

Türü içerdiğinden belirtilen türü bir değişkene atanamaz `auto` anahtar sözcüğü ve varsayılan [/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkindir.

## <a name="example"></a>Örnek

Değişkenleri içeren bir tür cast çünkü aşağıdaki kod C3537 verir `auto` anahtar sözcüğü.

```
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)