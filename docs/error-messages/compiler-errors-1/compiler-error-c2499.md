---
title: Derleyici hatası C2499
ms.date: 11/04/2016
f1_keywords:
- C2499
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
ms.openlocfilehash: 29fbb691304f9fc101f2367e014ae1e4e2231ff0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756987"
---
# <a name="compiler-error-c2499"></a>Derleyici hatası C2499

' class ': bir sınıf kendi taban sınıfı olamaz

Temel sınıf olarak tanımladığınız sınıfı belirtmeye çalıştınız.

Aşağıdaki örnek C2499 oluşturur:

```cpp
// C2499.cpp
// compile with: /c
class CMyClass : public CMyClass {};   // C2499
class CMyClass{};   // OK
```
