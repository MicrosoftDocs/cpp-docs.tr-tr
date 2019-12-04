---
title: Derleyici hatası C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: 894167fce43147b98af6603cba3102e5714b850e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746493"
---
# <a name="compiler-error-c2518"></a>Derleyici hatası C2518

' anahtar sözcüğü ' anahtar sözcüğü taban sınıf listesinde geçersizdir; LIP

`class` ve `struct` anahtar sözcükleri bir temel sınıf listesinde görünmemelidir.

Aşağıdaki örnek C2518 oluşturur:

```cpp
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```
