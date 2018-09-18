---
title: Derleyici Uyarısı (düzey 4) C4515 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4515
dev_langs:
- C++
helpviewer_keywords:
- C4515
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ae4fde16336b3bcd06b344641207b70279c7416
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037235"
---
# <a name="compiler-warning-level-4-c4515"></a>Derleyici Uyarısı (düzey 4) C4515

'ad alanı': ad alanı kendini kullanıyor

Kullanılan yinelemeli olarak bir ad alanıdır.

Aşağıdaki örnek, C4515 oluşturur:

```
// C4515.cpp
// compile with: /W4
namespace A
{
   using namespace A; // C4515
}

int main()
{
}
```