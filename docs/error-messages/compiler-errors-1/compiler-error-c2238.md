---
title: Derleyici Hatası C2238
ms.date: 11/04/2016
f1_keywords:
- C2238
helpviewer_keywords:
- C2238
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
ms.openlocfilehash: dde413c2c38e97fe47a0063953d64b0381d313a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442282"
---
# <a name="compiler-error-c2238"></a>Derleyici Hatası C2238

'token' öncesinde beklenmeyen belirteçler

Yanlış bir belirteç bulundu.

Aşağıdaki örnek, C2238 oluşturur:

```
// C2238.cpp
// compile with: /c
class v {
virtual: int vvv;   // C2238
};
```