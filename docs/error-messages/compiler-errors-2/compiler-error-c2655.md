---
title: Derleyici Hatası C2655
ms.date: 11/04/2016
f1_keywords:
- C2655
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
ms.openlocfilehash: 094dabb5ad07796194ae391000ca1e9025602d93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161192"
---
# <a name="compiler-error-c2655"></a>Derleyici Hatası C2655

'identifier': tanım veya geçerli kapsamda geçersiz yeniden bildirimi

Bir tanımlayıcı yalnızca genel kapsamda yeniden tanımlanıyor.

Aşağıdaki örnek, C2655 oluşturur:

```
// C2655.cpp
class A {};
class B {
public:
   static int i;
};

int B::i;  // OK

int main() {
   A B::i;  // C2655
}
```