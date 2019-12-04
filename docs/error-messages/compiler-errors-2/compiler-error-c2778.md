---
title: Derleyici hatası C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 247aba1b4dfe6b6d6db1e2b8f46f2aa08abf1a79
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739993"
---
# <a name="compiler-error-c2778"></a>Derleyici hatası C2778

__declspec (uuid ()) içinde hatalı biçimlendirilmiş GUID

[UUID](../../cpp/uuid-cpp.md) genişletilmiş özniteliğine yanlış bir GUID sağlandı.

GUID, aşağıdaki biçime sahip bir onaltılı sayı dizesi olmalıdır:

```cpp
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

`uuid` Extended özniteliği [Clsidfromstring](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)tarafından tanınan ve küme ayracı sınırlayıcıları olan veya olmayan dizeleri kabul eder.

Aşağıdaki örnek C2778 oluşturur:

```cpp
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```
