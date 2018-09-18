---
title: Derleyici Hatası C2236 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2236
dev_langs:
- C++
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fba2f795c3b786e82331a4b14f2c4530731db64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053706"
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