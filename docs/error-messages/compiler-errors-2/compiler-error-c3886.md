---
title: Derleyici Hatası C3886 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3886
dev_langs:
- C++
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 593c7e71c315801bcf080b60916a92d72ac32cd4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064047"
---
# <a name="compiler-error-c3886"></a>Derleyici Hatası C3886

'var': sabit değerli veri üyesi başlatılmalıdır

A [değişmez değer](../../windows/literal-cpp-component-extensions.md) declaraed olduğunda değişkeni'nin başlatılması gerekir.

Aşağıdaki örnek, C3886 oluşturur:

```
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```