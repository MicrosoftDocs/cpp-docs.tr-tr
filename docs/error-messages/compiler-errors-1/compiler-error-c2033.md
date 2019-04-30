---
title: Derleyici Hatası C2033
ms.date: 11/04/2016
f1_keywords:
- C2033
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
ms.openlocfilehash: 8147c707c70e6c3f21ed81b2acf0a59b72065408
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400493"
---
# <a name="compiler-error-c2033"></a>Derleyici Hatası C2033

'identifier': bit alanında yöneltme olamaz

Bit alanı verilmeyen bir işaretçi olarak bildirildi.

Aşağıdaki örnek, C2033 oluşturur:

```
// C2033.cpp
struct S {
   int *b : 1;  // C2033
};
```

Olası çözüm:

```
// C2033b.cpp
// compile with: /c
struct S {
   int b : 1;
};
```