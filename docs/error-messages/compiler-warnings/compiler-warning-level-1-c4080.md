---
title: Derleyici Uyarısı (düzey 1) C4080
ms.date: 11/04/2016
f1_keywords:
- C4080
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
ms.openlocfilehash: 5ecc50d4f967826cca691fae4f119c1dee2efef5
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626887"
---
# <a name="compiler-warning-level-1-c4080"></a>Derleyici Uyarısı (düzey 1) C4080

kesim adı için tanımlayıcı bekleniyordu; ' symbol ' bulundu

[#Pragma alloc_text](../../preprocessor/alloc-text.md) içindeki segmentin adı bir dize veya tanımlayıcı olmalıdır. Geçerli bir tanımlayıcı bulunamazsa derleyici pragma öğesini yoksayar.

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