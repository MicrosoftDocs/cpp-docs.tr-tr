---
title: Derleyici Hatası C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 379bcc7f37ff8942e4e45c6a6188438400937875
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187912"
---
# <a name="compiler-error-c2348"></a>Derleyici Hatası C2348

'type name': C stili bir toplama değil; katıştırılmış IDL ile dışarı aktarılamaz

Yerleştirmek için bir `struct` bir .idl dosyasında [dışarı](../../windows/export.md) özniteliği `struct` yalnızca verileri içermelidir.

Aşağıdaki örnek, C2348 oluşturur:

```
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