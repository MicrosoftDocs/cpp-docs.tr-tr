---
title: Derleyici Hatası C2506 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2506
dev_langs:
- C++
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4967c410dfdce781a4191c9ac848883228ba4d3a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093421"
---
# <a name="compiler-error-c2506"></a>Derleyici Hatası C2506

'member': '__declspec(modifier)' bu simgeye uygulanamaz

Statik bir yönetilen sınıf üyeleri için işlem içi appdomain başına bildiremezsiniz.

Bkz: [appdomain](../../cpp/appdomain.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2506 oluşturur.

```
// C2506.cpp
// compile with: /clr /c
ref struct R {
   __declspec(process) static int n;   // C2506
   int o;   // OK
};
```