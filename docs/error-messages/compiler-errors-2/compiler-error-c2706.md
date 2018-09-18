---
title: Derleyici Hatası C2706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2706
dev_langs:
- C++
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 560edb9953d4f7c751f4ab4102fd544fb09bb86d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066017"
---
# <a name="compiler-error-c2706"></a>Derleyici Hatası C2706

eşleşen olmadan __except geçersizdir \__try (eksik '}' içinde \__try blok?)

Derleyici için bir kapanış ayracı bulamadı bir `__try` blok.

Aşağıdaki örnek, C2706 oluşturur:

```
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```