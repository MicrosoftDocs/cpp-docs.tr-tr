---
title: Derleyici Hatası C2438 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2438
dev_langs:
- C++
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f5153e3ff6626f3ea1b1155f14bc9ef96441e7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066082"
---
# <a name="compiler-error-c2438"></a>Derleyici Hatası C2438

'identifier': statik sınıf verileri Oluşturucu başlatılamıyor

Bir oluşturucu, bir sınıfın statik bir üye başlatmak için kullanılır. Statik üyeleri sınıf bildirimi dışında bir tanımı başlatılmalıdır.

Aşağıdaki örnek, C2438 oluşturur:

```
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```