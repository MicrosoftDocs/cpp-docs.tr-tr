---
title: Derleyici Hatası C3239 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3239
dev_langs:
- C++
helpviewer_keywords:
- C3239
ms.assetid: 22a518b7-020f-4f3c-9963-a094667fd1ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f1d3c405e7a74dbade84b0ecd25284c4d6d8f27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093863"
---
# <a name="compiler-error-c3239"></a>Derleyici Hatası C3239

'type': işaretçi iç/tam işaretçiye ortak dil çalışma zamanı tarafından izin verilmiyor

Derleyici, geçersiz bir türe karşılaşıldı.

Aşağıdaki örnek, C3229 oluşturur:

```
// C3239.cpp
// compile with: /clr
int main() {
   interior_ptr<int>* pip0;   // C3239

   // OK
   int * pip1;
   interior_ptr<int> pip2;
   int ** pip;
}
```