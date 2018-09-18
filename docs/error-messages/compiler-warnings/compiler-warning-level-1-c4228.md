---
title: Derleyici Uyarısı (düzey 1) C4228 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4228
dev_langs:
- C++
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab568ef6622bfa10f0e10566ec92dfaee71d22c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047960"
---
# <a name="compiler-warning-level-1-c4228"></a>Derleyici Uyarısı (düzey 1) C4228

Standart olmayan uzantı kullanıldı: bildirimci listesinde virgülden sonraki niteleyiciler yoksayıldı

Niteleyiciler kullanımını ister **const** veya `volatile` sonra bir virgül değişkenleri bildirirken bir Microsoft uzantısıdır ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Örnek

```
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```