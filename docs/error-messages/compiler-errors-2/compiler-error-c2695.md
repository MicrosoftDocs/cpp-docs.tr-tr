---
title: Derleyici hatası C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6d46699a2036c4f45daf3c34802ddb6b44e554ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755219"
---
# <a name="compiler-error-c2695"></a>Derleyici hatası C2695

' işlev1 ': geçersiz kılan sanal işlev yalnızca çağırma kuralına göre ' function2 ' öğesinden farklıdır

Türetilmiş sınıftaki bir işlevin imzası, temel sınıftaki bir işlevi geçersiz kılamaz ve çağırma kuralını değiştiremezler.

Aşağıdaki örnek C2695 oluşturur:

```cpp
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```
