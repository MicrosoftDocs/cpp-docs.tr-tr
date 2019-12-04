---
title: Derleyici hatası C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: 6f60a9abbc5702c1a0d14d0f894c9b1684378c3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759366"
---
# <a name="compiler-error-c3238"></a>Derleyici hatası C3238

' Type ': Bu ada sahip bir tür, ' Assembly ' derlemesine zaten iletildi

Bir tür, başvurulan bir derlemede tür iletme söz dizimi aracılığıyla tanımlanan bir istemci uygulamasında tanımlanmıştır. Her iki tür de uygulamanın kapsamında tanımlanamaz.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek, başka bir derlemeden iletilen bir türü içeren bir derleme oluşturur.

```cpp
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, tür tanımını içeren, ancak yalnızca tür iletme sözdizimini içermeyen bir derleme oluşturur.

```cpp
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C3238 oluşturur.

```cpp
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```
