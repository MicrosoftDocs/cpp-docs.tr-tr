---
title: Derleyici Hatası C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 8c09ea34c7dabf2cadecad7c76d766c9496f5a5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461015"
---
# <a name="compiler-error-c3286"></a>Derleyici Hatası C3286

> '*belirticisi*': bir yineleme değişkeninin herhangi bir depolama sınıfı tanımlayıcıları olamaz

Bir depolama sınıfı üzerinde yineleme değişkeni belirtilemez. Daha fazla bilgi için [depolama sınıfları (C++)](../../cpp/storage-classes-cpp.md) ve [her, içinde](../../dotnet/for-each-in.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3286 oluşturur ve ayrıca doğru kullanımını gösterir.

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```