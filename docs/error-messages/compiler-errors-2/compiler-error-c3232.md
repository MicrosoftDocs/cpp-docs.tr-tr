---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3232'
title: Derleyici hatası C3232
ms.date: 11/04/2016
f1_keywords:
- C3232
helpviewer_keywords:
- C3232
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
ms.openlocfilehash: 180af73cc76afdca9d21c168e925bc1755cd88a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312013"
---
# <a name="compiler-error-c3232"></a>Derleyici hatası C3232

' param ': bir genel tür parametresi nitelenmiş adda kullanılamaz

Genel tür parametresi yanlış kullanıldı.

Aşağıdaki örnek C3232 oluşturur:

```cpp
// C3232.cpp
// compile with: /clr
generic <class T>
ref class C {
   typename T::TYPE t;   // C3232
};
```
