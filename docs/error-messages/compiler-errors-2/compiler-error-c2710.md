---
title: Derleyici Hatası C2710 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2710
dev_langs:
- C++
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94b95ce0a87a2ba894dde2ba41c0e7d704c477b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112804"
---
# <a name="compiler-error-c2710"></a>Derleyici Hatası C2710

'oluşturmak': '__declspec(modifier)' yalnızca işaretçi döndüren bir işleve uygulanabilir

Dönüş değeri olan bir işaretçi bir işlev, yalnızca yapıdır `modifier` uygulanabilir.

Aşağıdaki örnek, C2710 oluşturur:

```
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```