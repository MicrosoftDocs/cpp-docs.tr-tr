---
title: Derleyici Uyarısı (düzey 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: 58f7150caeb3e06ba400a08c6e484f677a8deff9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051383"
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