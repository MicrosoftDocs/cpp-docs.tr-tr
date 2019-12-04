---
title: Derleyici hatası C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 7bded618c481e59f60c5528510c757dec7226acc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760003"
---
# <a name="compiler-error-c2348"></a>Derleyici hatası C2348

' tür adı ': C stili bir toplama değil; katıştırılmış IDL içinde verilemez

[Dışarı aktarma](../../windows/export.md) özniteliğiyle bir. IDL dosyasına bir `struct` yerleştirmek için, `struct` yalnızca Data içermelidir.

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
