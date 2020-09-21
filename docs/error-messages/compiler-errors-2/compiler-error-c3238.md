---
title: Derleyici hatası C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: 1f238a3be27023c755544438166aae1b2b2967d3
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741989"
---
# <a name="compiler-error-c3238"></a>Derleyici hatası C3238

' Type ': Bu ada sahip bir tür, ' Assembly ' derlemesine zaten iletildi

Bir tür, başvurulan bir derlemede tür iletme söz dizimi aracılığıyla tanımlanan bir istemci uygulamasında tanımlanmıştır. Her iki tür de uygulamanın kapsamında tanımlanamaz.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) .

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, başka bir derlemeden iletilen bir türü içeren bir derleme oluşturur.

```cpp
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

Aşağıdaki örnek, tür tanımını içeren, ancak yalnızca tür iletme sözdizimini içermeyen bir derleme oluşturur.

```cpp
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

Aşağıdaki örnek C3238 oluşturur.

```cpp
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```
