---
title: Derleyici Hatası C2655 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2655
dev_langs:
- C++
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 456fd31e6d618774bff13c9800d6a44ffd3deb73
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078692"
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