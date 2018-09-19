---
title: Derleyici Hatası C3232 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3232
dev_langs:
- C++
helpviewer_keywords:
- C3232
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e7b3e8c306b8e883fd3edb0b2781b297842bb0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018372"
---
# <a name="compiler-error-c3232"></a>Derleyici Hatası C3232

'param': genel tür parametresi bir nitelenmiş adda kullanılamaz

Genel tür parametresi yanlış kullanıldı.

Aşağıdaki örnek, C3232 oluşturur:

```
// C3232.cpp
// compile with: /clr
generic <class T>
ref class C {
   typename T::TYPE t;   // C3232
};
```