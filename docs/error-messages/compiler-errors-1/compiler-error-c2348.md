---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2348'
title: Derleyici hatası C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 829bd94c8fe78280b8b49b74f218e2143dda4335
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298363"
---
# <a name="compiler-error-c2348"></a>Derleyici hatası C2348

' tür adı ': C stili bir toplama değil; katıştırılmış IDL içinde verilemez

**`struct`** [Dışa aktarma](../../windows/attributes/export.md) özniteliğiyle bir. IDL dosyasına yerleştirmek için, **`struct`** yalnızca verileri içermelidir.

Aşağıdaki örnek C2348 oluşturur:

```cpp
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```
