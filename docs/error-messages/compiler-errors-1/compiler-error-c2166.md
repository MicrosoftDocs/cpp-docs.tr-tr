---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2166'
title: Derleyici hatası C2166
ms.date: 11/04/2016
f1_keywords:
- C2166
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
ms.openlocfilehash: 195782fca62b9bf69d17fa1aa382df2127b594e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145527"
---
# <a name="compiler-error-c2166"></a>Derleyici hatası C2166

l-değeri const nesnesi belirtiyor

Kod, belirtilen bir öğeyi değiştirmeye çalışır **`const`** .

Aşağıdaki örnek C2166 oluşturur:

```cpp
// C2166.cpp
int f();
int main() {
   ( (const int&) 1 ) = 5;   // C2166
}
```
