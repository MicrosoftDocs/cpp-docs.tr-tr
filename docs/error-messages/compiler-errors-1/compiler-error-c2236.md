---
title: Derleyici Hatası C2236
ms.date: 11/04/2016
f1_keywords:
- C2236
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
ms.openlocfilehash: 988377d2995468c84b86872ab6f2b25f5c3df9f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462653"
---
# <a name="compiler-error-c2236"></a>Derleyici Hatası C2236

beklenmeyen belirteç 'identifier'. Unuttunuz bir ';'?

Tanımlayıcı zaten bir türü olarak tanımlanmış ve kullanıcı tanımlı bir tür tarafından geçersiz kılınamaz.

Aşağıdaki örnek, C2236 oluşturur:

```
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```