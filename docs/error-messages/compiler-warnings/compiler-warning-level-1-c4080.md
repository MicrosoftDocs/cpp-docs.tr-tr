---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4080'
title: Derleyici Uyarısı (düzey 1) C4080
ms.date: 11/04/2016
f1_keywords:
- C4080
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
ms.openlocfilehash: 05dcb119d0c028446f038a2cbd796432c688a8c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344295"
---
# <a name="compiler-warning-level-1-c4080"></a>Derleyici Uyarısı (düzey 1) C4080

kesim adı için tanımlayıcı bekleniyordu; ' symbol ' bulundu

[#Pragma alloc_text](../../preprocessor/alloc-text.md) segmentinin adı bir dize veya tanımlayıcı olmalıdır. Geçerli bir tanımlayıcı bulunamazsa derleyici pragma öğesini yoksayar.

Aşağıdaki örnek C4080 oluşturur:

```cpp
// C4080.cpp
// compile with: /W1
extern "C" void func(void);

#pragma alloc_text()   // C4080

// try this line to resolve the warning
// #pragma alloc_text("mysection", func)

int main() {
}

void func(void) {
}
```
