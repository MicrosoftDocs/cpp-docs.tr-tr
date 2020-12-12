---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2380'
title: Derleyici hatası C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: 4455fef072b6d8f686d5f43130db8d02aba69fd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174695"
---
# <a name="compiler-error-c2380"></a>Derleyici hatası C2380

' Identifier ' öncesinde tür (dönüş türü olan Oluşturucu veya geçerli sınıf adı için geçersiz yeniden tanımlama mi var?)

Bir Oluşturucu bir değer döndürür veya sınıf adını tekrar tanımlar.

Aşağıdaki örnek C2326 oluşturur:

```cpp
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```
