---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2589'
title: Derleyici hatası C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: b874988f65ef41a9cde19e4c0229a6cb54859b28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177503"
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
