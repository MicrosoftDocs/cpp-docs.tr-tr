---
title: Derleyici hatası C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 0816fcb4d9e2a3e6588dfcf937383fed7ab11395
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737133"
---
# <a name="compiler-error-c2530"></a>Derleyici hatası C2530

' tanımlayıcı ': başvuruların başlatılması gerekir

Zaten bildirilemediği takdirde, bildirildiği zaman bir başvuru başlatmalısınız:

- [Dış](../../cpp/using-extern-to-specify-linkage.md)anahtar sözcüğü ile.

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
