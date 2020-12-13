---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2691'
title: Derleyici hatası C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 575651d1da871a0514585fea010ef3fe98e8a3cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344334"
---
# <a name="compiler-error-c2691"></a>Derleyici hatası C2691

' veri türü ': yönetilen veya WinRTarray bu öğe türüne sahip olamaz

Yönetilen veya WinRT dizi öğesinin türü bir değer türü veya bir başvuru türü olabilir.

Aşağıdaki örnek C2691 oluşturur:

```cpp
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
