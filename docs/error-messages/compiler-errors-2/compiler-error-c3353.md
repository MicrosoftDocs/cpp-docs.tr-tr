---
title: Derleyici Hatası C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: eb7b55f63e911f155c13e777e2e84ae7b587e9a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432675"
---
# <a name="compiler-error-c3353"></a>Derleyici Hatası C3353

'temsilci': bir temsilci yalnızca genel bir işlev veya bir üye işlevi bir yönetilen veya WinRT türü oluşturulabilir

Temsilciler, bildirilen ile [temsilci](../../windows/delegate-cpp-component-extensions.md) anahtar sözcüğü, yalnızca genel kapsamda bildirilebilir.

Aşağıdaki örnek, C3353 oluşturur:

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```