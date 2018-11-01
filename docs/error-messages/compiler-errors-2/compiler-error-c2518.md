---
title: Derleyici Hatası C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: d0a1f7bdc493a16b38dc2348097cc6cbea7ed898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657216"
---
# <a name="compiler-error-c2518"></a>Derleyici Hatası C2518

anahtar sözcüğü 'anahtar sözcüğü' taban sınıfı listesinde; geçersiz yoksayıldı

Anahtar sözcükler `class` ve `struct` bir temel sınıf listesinde görünmemelidir.

Aşağıdaki örnek, C2518 oluşturur:

```
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```