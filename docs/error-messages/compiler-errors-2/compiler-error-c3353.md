---
title: Derleyici Hatası C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: c38642d7abd4f2fd50792c548c9a5521b2da10ad
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776147"
---
# <a name="compiler-error-c3353"></a>Derleyici Hatası C3353

'temsilci': bir temsilci yalnızca genel bir işlev veya bir üye işlevi bir yönetilen veya WinRT türü oluşturulabilir

Temsilciler, bildirilen ile [temsilci](../../extensions/delegate-cpp-component-extensions.md) anahtar sözcüğü, yalnızca genel kapsamda bildirilebilir.

Aşağıdaki örnek, C3353 oluşturur:

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```