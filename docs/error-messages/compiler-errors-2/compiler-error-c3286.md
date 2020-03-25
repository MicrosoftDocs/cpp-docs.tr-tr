---
title: Derleyici hatası C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 4c87e98f11a560d0d92be8ea7bc624edd4e09ad2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201402"
---
# <a name="compiler-error-c3286"></a>Derleyici hatası C3286

> '*belirtici*': bir yineleme değişkeni hiçbir depolama sınıfı belirticisine sahip olamaz

Bir yineleme değişkeninde bir depolama sınıfı belirtilemez. Daha fazla bilgi için, bkz. [depolamaC++sınıfları ()](../../cpp/storage-classes-cpp.md) ve [için](../../dotnet/for-each-in.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3286 oluşturur ve ayrıca doğru kullanımı gösterir.

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```
