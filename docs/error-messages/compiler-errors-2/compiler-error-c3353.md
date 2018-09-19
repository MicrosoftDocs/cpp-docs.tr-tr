---
title: Derleyici Hatası C3353 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63316a5a74c3981ec0f68d949eba654f8d6bbfef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110204"
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