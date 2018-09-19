---
title: Derleyici Hatası C3919 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3919
dev_langs:
- C++
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 565146e714e0aa9a3598e4fe5fdeea361454ec78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136120"
---
# <a name="compiler-error-c3919"></a>Derleyici Hatası C3919

'event_method': işlevin türü 'type' olmalıdır

Bir olay erişimci yöntemini doğru olarak bildirilmedi.

Olaylar hakkında daha fazla bilgi için bkz. [olay](../../windows/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3919 oluşturur:

```
// C3919.cpp
// compile with: /clr /c
using namespace System;
delegate void D(String^);
ref class R {
   event D^ e {
      int add(int);   // C3919
      int remove(int);   // C3919

      void add(D^);   // OK
      void remove(D^);   // OK
   }
};
```