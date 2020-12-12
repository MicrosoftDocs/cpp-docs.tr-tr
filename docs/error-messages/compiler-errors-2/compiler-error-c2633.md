---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2633'
title: Derleyici hatası C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: 182cafdd9a79744414a89792e1361c8173077705
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123454"
---
# <a name="compiler-error-c2633"></a>Derleyici hatası C2633

' tanımlayıcı ': ' inline ' oluşturucular için tek geçerli depolama sınıfıdır

Bir Oluşturucu, satır içi dışında bir depolama sınıfı olarak bildirilmiştir.

Aşağıdaki örnek C2633 oluşturur:

```cpp
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```
