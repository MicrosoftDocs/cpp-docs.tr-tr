---
title: Derleyici hatası C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 4eca5579f6bf132452a813d8dd99193df5f76b92
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500536"
---
# <a name="compiler-error-c2530"></a>Derleyici hatası C2530

' tanımlayıcı ': başvuruların başlatılması gerekir

Zaten bildirilemediği takdirde, bildirildiği zaman bir başvuru başlatmalısınız:

- [Dış](../../cpp/extern-cpp.md)anahtar sözcüğü ile.

- Bir sınıf, yapı veya birleşimin üyesi olarak (ve oluşturucuda başlatılır).

- Bir işlev bildiriminde veya tanımında parametre olarak.

- Bir işlevin dönüş türü olarak.

Aşağıdaki örnek C2530 oluşturur:

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
