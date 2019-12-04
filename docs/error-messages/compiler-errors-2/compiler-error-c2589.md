---
title: Derleyici hatası C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: 76cc35e57c1577ed23c043740f37c602600da542
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748508"
---
# <a name="compiler-error-c2589"></a>Derleyici hatası C2589

' tanımlayıcı ': ':: ' sağ tarafında geçersiz belirteç

Bir sınıf, yapı veya birleşim adı, kapsam çözümleme işlecinin sol tarafında (çift iki nokta üst üste) görünürse, sağdaki belirtecin bir sınıf, yapı veya birleşim üyesi olması gerekir. Aksi takdirde, herhangi bir genel tanımlayıcı sağ tarafta görünebilir.

Kapsam çözümleme işleci aşırı yüklenemez.

Aşağıdaki örnek C2589 oluşturur:

```cpp
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```
