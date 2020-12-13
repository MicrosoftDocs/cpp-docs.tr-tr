---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4309'
title: Derleyici Uyarısı (düzey 2) C4309
ms.date: 11/04/2016
f1_keywords:
- C4309
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
ms.openlocfilehash: 8ae49967078f8569a7830c2a2e2ce61f9d25e20d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339175"
---
# <a name="compiler-warning-level-2-c4309"></a>Derleyici Uyarısı (düzey 2) C4309

' dönüştürme ': sabit değer kesilmesi

Tür dönüştürme bir sabite ayrılan alanı aşmasına neden olur. Sabit için daha büyük bir tür kullanmanız gerekebilir.

Aşağıdaki örnek C4309 oluşturur:

```cpp
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```
