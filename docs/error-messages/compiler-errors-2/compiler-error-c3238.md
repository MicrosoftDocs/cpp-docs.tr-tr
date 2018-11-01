---
title: Derleyici Hatası C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: d81fd0fb3612a8c22fa6365aa7fc6dddb89cf120
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481165"
---
# <a name="compiler-error-c3238"></a>Derleyici Hatası C3238

'type': 'derleme' derlemesi için bu ada sahip bir tür zaten iletilmiş

Bir tür, başvurulan bir derleme söz dizimi iletme türü ile tanımlanmış bir istemci uygulamasında tanımlandı. Her iki tür uygulama kapsamı içinde tanımlanamaz.

Bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, başka bir derleme iletilen türü içeren bir derleme oluşturur.

```
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, tür tanımını kapsamak için kullanılmış bir derleme oluşturur, ancak yalnızca söz dizimi iletme türü içeriyor.

```
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3238 oluşturur.

```
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```