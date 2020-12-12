---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2695'
title: Derleyici hatası C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6137749725de5c2285cb5defd84fd7c8c0f2e237
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326649"
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
