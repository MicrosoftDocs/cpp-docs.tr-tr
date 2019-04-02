---
title: Derleyici Hatası C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 24f17d2990c9258168a6d37fef101c21f62cb08d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768659"
---
# <a name="compiler-error-c3215"></a>Derleyici Hatası C3215

'type1': genel tür parametresi 'type2' tarafından zaten kısıtlanmış

Kısıtlama birden çok kez belirtildi.

Genel türler hakkında daha fazla bilgi için bkz. [genel türler](../../extensions/generics-cpp-component-extensions.md).

Aşağıdaki örnek, C3215 oluşturur:

```
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

Olası çözüm:

```
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```