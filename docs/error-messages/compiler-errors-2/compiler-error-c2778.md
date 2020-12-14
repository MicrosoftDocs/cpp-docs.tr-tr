---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2778'
title: Derleyici hatası C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: e614ed5ee94a4876a687bfa8257abc5bcd9d8587
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298077"
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

`uuid`Genişletilmiş öznitelik, tanımlı parantez sınırlayıcıları olan veya olmayan [Clsidfromstring](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)tarafından tanınan dizeleri kabul eder.

Aşağıdaki örnek C2778 oluşturur:

```cpp
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```
