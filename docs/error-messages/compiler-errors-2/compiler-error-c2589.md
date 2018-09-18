---
title: Derleyici Hatası C2589 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2db5dde898a3e5918eed62b2b32231b5d7ed014f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046062"
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