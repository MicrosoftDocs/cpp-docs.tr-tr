---
title: Derleyici Uyarısı (düzey 4) C4245
ms.date: 11/04/2016
f1_keywords:
- C4245
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
ms.openlocfilehash: 3d55226a368f81a9506b38fe9271da4332bd1f5b
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541726"
---
# <a name="compiler-warning-level-4-c4245"></a>Derleyici Uyarısı (düzey 4) C4245

' dönüştürme ': ' type1 ' değerinden ' type2 ' öğesine dönüştürme, imzalanmış/imzasız uyuşmazlığı

Negatif değeri `unsigned`olan imzalı bir **const** 'i dönüştürmeye çalıştınız.

Aşağıdaki örnek C4245 oluşturur:

```cpp
// C4245.cpp
// compile with: /W4 /c
const int i = -1;
unsigned int j = i; // C4245

const int k = 1;
unsigned int l = k; // okay

int m = -1;
unsigned int n = m; // okay

void Test(size_t i) {}

int main() {
   Test( -19 );   // C4245
}
```