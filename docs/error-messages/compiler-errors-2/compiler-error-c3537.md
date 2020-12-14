---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3537'
title: Derleyici hatası C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 84440b757b85a59f87fcca064911136da6cce269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315263"
---
# <a name="compiler-error-c3537"></a>Derleyici hatası C3537

' tür ': ' Auto ' içeren bir türe dönüştüremezsiniz

Tür **`auto`** anahtar sözcüğünü içerdiğinden ve varsayılan [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkin olduğundan, belirtilen türe bir değişken atanamaz.

## <a name="example"></a>Örnek

Aşağıdaki kod, C3537 verir, çünkü değişkenler anahtar sözcüğünü içeren bir türe dönüştürülür **`auto`** .

```cpp
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

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)
