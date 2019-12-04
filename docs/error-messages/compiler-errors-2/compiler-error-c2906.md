---
title: Derleyici hatası C2906
ms.date: 11/04/2016
f1_keywords:
- C2906
helpviewer_keywords:
- C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
ms.openlocfilehash: bf21c4f14948d56fe781226e5aaf1b479059cb55
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748703"
---
# <a name="compiler-error-c2906"></a>Derleyici hatası C2906

' özelleşme ': açık özelleştirme ' Template < > ' gerektirir

Şablonların açık özelleştirmesi için yeni sözdizimini kullanmanız gerekir.

Aşağıdaki örnek C2906 oluşturur:

```cpp
// C2906.cpp
// compile with: /c
template<class T> class X{};   // primary template
class X<int> { }   // C2906
template<> class X<int> { };   // new syntax
```
