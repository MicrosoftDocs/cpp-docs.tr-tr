---
title: Derleyici Hatası C3912 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3912
dev_langs:
- C++
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26ffa49a6b54769db5b24d91ffcaf72579a6e458
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115261"
---
# <a name="compiler-error-c3912"></a>Derleyici Hatası C3912

'event': olayın türü bir temsilci türü olmalıdır

Bir olay olarak bildirildi, ancak doğru türde değildi.

Daha fazla bilgi için [olay](../../windows/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3912 oluşturur:

```
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```