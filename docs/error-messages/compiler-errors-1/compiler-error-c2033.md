---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2033'
title: Derleyici hatası C2033
ms.date: 11/04/2016
f1_keywords:
- C2033
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
ms.openlocfilehash: c7beabafb544f1ad76f6a8eabe24bd20a7e63f62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175436"
---
# <a name="compiler-error-c2033"></a>Derleyici hatası C2033

' tanımlayıcı ': bit alanında yöneltme olamaz

Bit alanı bir işaretçi olarak bildirildi; buna izin verilmez.

Aşağıdaki örnek C2033 oluşturur:

```cpp
// C2033.cpp
struct S {
   int *b : 1;  // C2033
};
```

Olası çözüm:

```cpp
// C2033b.cpp
// compile with: /c
struct S {
   int b : 1;
};
```
