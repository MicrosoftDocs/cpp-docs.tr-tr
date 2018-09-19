---
title: Derleyici Hatası C3152 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3152
dev_langs:
- C++
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 975ce5a948305f5b2538496ddef34e18bb6db63c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079693"
---
# <a name="compiler-error-c3152"></a>Derleyici Hatası C3152

'oluşturmak': 'anahtar sözcüğü', yalnızca bir sınıf, yapı veya sanal üye işleve uygulanabilir

Bazı anahtar sözcükler yalnızca bir C++ sınıfı için uygulanabilir.

Aşağıdaki örnek, C3152 oluşturur ve bu sorunun nasıl gösterir:

```
// C3152.cpp
// compile with: /clr /c
ref class C {
   int (*pfn)() sealed;   // C3152
   virtual int g() sealed;   // OK
};
```
