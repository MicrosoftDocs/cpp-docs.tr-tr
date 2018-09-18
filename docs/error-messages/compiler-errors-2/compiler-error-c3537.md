---
title: Derleyici Hatası C3537 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3537
dev_langs:
- C++
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f04500998adf132594b91fc38f82c8bec4b1c5c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107698"
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

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)