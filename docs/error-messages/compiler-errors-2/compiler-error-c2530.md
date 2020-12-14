---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2530'
title: Derleyici hatası C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 07980fb6d87b4e84bc0b253ccd317eba02fa81af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258115"
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
