---
title: Derleyici Hatası C2499
ms.date: 11/04/2016
f1_keywords:
- C2499
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
ms.openlocfilehash: 645dd3923e65240de17803a8831a0223ff0e1656
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360560"
---
# <a name="compiler-error-c2499"></a>Derleyici Hatası C2499

'class': bir sınıf kendisinin taban sınıfı olamaz

Temel sınıf olarak tanımladığınız sınıf belirtin çalışıldı.

Aşağıdaki örnek, C2499 oluşturur:

```
// C2499.cpp
// compile with: /c
class CMyClass : public CMyClass {};   // C2499
class CMyClass{};   // OK
```