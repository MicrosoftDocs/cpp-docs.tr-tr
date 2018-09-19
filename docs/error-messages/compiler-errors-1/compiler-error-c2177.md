---
title: Derleyici Hatası C2177 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2177
dev_langs:
- C++
helpviewer_keywords:
- C2177
ms.assetid: 2a39a880-cddb-4d3e-a572-645a14c4c478
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42d002b2264c9ce6b5e8d09dcda322c33b18fd05
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096164"
---
# <a name="compiler-error-c2177"></a>Derleyici Hatası C2177

Sabit çok büyük

Sabit değer, atanmış olduğu değişken türü için çok büyük.

Aşağıdaki örnek, C2177 oluşturur:

```
// C2177.cpp
int main() {
   int a=18446744073709551616;   // C2177
   int b=18446744073709551615;   // OK
}
```