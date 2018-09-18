---
title: Derleyici Hatası C2846 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2846
dev_langs:
- C++
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f062445aac010b5ba1ac34129590edf7b1f16932
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067382"
---
# <a name="compiler-error-c2846"></a>Derleyici Hatası C2846

'Oluşturucu': arabirimin Oluşturucusu olamaz

Visual C++ [arabirimi](../../cpp/interface.md) Oluşturucusu olamaz.

Aşağıdaki örnek, C2846 oluşturur:

```
// C2846.cpp
// compile with: /c
__interface C {
   C();   // C2846 constructor not allowed in an interface
};
```