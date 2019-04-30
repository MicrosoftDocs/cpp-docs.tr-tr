---
title: Derleyici Hatası C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: 18d8f7130c34f5e1e33bc7aa9b9463f50c243045
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386947"
---
# <a name="compiler-error-c2589"></a>Derleyici Hatası C2589

'identifier': sağ tarafında geçersiz belirteç '::'

Bir sınıf, yapı veya birleşim adı sol tarafında kapsam çözümleme işleci (çift iki nokta üst üste) görünürse, sağdaki belirteci bir sınıf, yapı veya birleşim üyesi olması gerekir. Aksi takdirde, herhangi bir genel tanımlayıcı sağ tarafta görünür.

Kapsam çözümleme işleci aşırı yüklenemez.

Aşağıdaki örnek, C2589 oluşturur:

```
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```