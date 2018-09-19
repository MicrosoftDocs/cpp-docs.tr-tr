---
title: Derleyici Hatası C2443 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2443
dev_langs:
- C++
helpviewer_keywords:
- C2443
ms.assetid: 315330d5-24bc-4193-a531-0642095be58f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10592e3e6fc5a5b2c07f2067e3f798d7cda507bd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102430"
---
# <a name="compiler-error-c2443"></a>Derleyici Hatası C2443

işlenen boyutu çelişkisi

Yönerge işlenenler aynı boyutta olmasını gerektirir.

Aşağıdaki örnek, C2443 oluşturur:

```
// C2443.cpp
// processor: x86
short var;
int main() {
   __asm xchg ax,bl   // C2443
   __asm mov al,red   // C2443
   __asm mov al,BYTE PTR var   // OK
}
```