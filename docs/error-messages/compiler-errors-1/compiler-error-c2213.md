---
title: Derleyici Hatası C2213 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2213
dev_langs:
- C++
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55bf3cb315ff2b65f4c65ff1091cd530cd810fd7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096073"
---
# <a name="compiler-error-c2213"></a>Derleyici Hatası C2213

'değiştiricisi': __based için geçersiz bağımsız değişken

Bağımsız değişken değiştirme `__based` geçersiz.

Aşağıdaki örnek, C2213 oluşturur:

```
// C2213.cpp
// compile with: /c
int i;
int *j;
char __based(i) *p;   // C2213
char __based(j) *p2;   // OK
```