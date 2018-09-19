---
title: Derleyici Hatası C2428 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2428
dev_langs:
- C++
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac8b176db26ed615874569a9ed646b9d89ec4db0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097945"
---
# <a name="compiler-error-c2428"></a>Derleyici Hatası C2428

'operation': 'bool' türü işlenen üzerinde izin verilmiyor

Azaltma işleci türündeki nesnelere uygulayamazsınız `bool`.

Aşağıdaki örnek, C2428 oluşturur:

```
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```