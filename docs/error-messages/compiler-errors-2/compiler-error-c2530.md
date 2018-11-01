---
title: Derleyici Hatası C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 2c8164cad25d68ee61ff9fed7170482d5dfc9505
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474795"
---
# <a name="compiler-error-c2530"></a>Derleyici Hatası C2530

'identifier': başvuruların başlatılması gerekir

Bunu bildirildi, zaten bildirildiği sürece bir başvuruyu başlatmak gerekir:

- Anahtar sözcüğü ile [extern](../../cpp/using-extern-to-specify-linkage.md).

- Bir sınıf, yapı veya birleşim üyesi olarak (ve oluşturucuda başlatılır).

- Bir işlev bildirimini veya tanımını parametre olarak.

- Bir işlevin dönüş türü olarak.

Aşağıdaki örnek, C2530 oluşturur:

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```