---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4669'
title: Derleyici Uyarısı (düzey 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: 590c013aed522544462141346ed9b58991d26ed3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164321"
---
# <a name="compiler-warning-level-1-c4669"></a>Derleyici Uyarısı (düzey 1) C4669

' cast ': güvenli olmayan dönüştürme: ' class ' bir yönetilen veya WinRT türü nesnesidir

Bir tür dönüştürme Windows Çalışma Zamanı veya yönetilen bir tür içerir. Derleyici, diğerinin bir işaretçisinin bit temelinde bir kopyasını gerçekleştirerek dönüştürmeyi tamamlar, ancak başka bir denetim sağlamaz. Bu uyarıyı çözmek için, yönetilen üyeleri veya Windows Çalışma Zamanı türlerini içeren sınıfları atama.

Aşağıdaki örnek C4669 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4669.cpp
// compile with: /clr /W1
ref struct A {
   int i;
   Object ^ pObj;   // remove the managed member to fix the warning
};

ref struct B {
   int j;
};

int main() {
   A ^ a = gcnew A;
   B ^ b = reinterpret_cast<B ^>(a);   // C4669
}
```
