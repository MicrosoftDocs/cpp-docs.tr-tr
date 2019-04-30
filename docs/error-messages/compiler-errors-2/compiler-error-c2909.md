---
title: Derleyici Hatası C2909
ms.date: 11/04/2016
f1_keywords:
- C2909
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
ms.openlocfilehash: 7a777e87d8110ac16740346a8494f9501ce93b37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404292"
---
# <a name="compiler-error-c2909"></a>Derleyici Hatası C2909

'identifier': işlev şablonunun açıkça örneğinin oluşturulması dönüş türü gerektirir

Bir işlev şablonunun açıkça örneğinin kendi dönüş türünün açık belirtimi gerektirir. Örtük dönüş türü belirtimi çalışmaz.

Aşağıdaki örnek, C2909 oluşturur:

```
// C2909.cpp
// compile with: /c
template<class T> int f(T);
template f<int>(int);         // C2909
template int f<int>(int);   // OK
```