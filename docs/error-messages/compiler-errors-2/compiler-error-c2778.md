---
title: Derleyici hatası C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 98b5bf0a1315236f3ce96fd4b8c140ce1ab70a9f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501044"
---
# <a name="compiler-error-c2778"></a>Derleyici hatası C2778

__declspec (uuid ()) içinde hatalı biçimlendirilmiş GUID

[UUID](../../cpp/uuid-cpp.md) genişletilmiş özniteliğine yanlış bir GUID sağlandı.

GUID, aşağıdaki biçime sahip bir onaltılı sayı dizesi olmalıdır:

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

Genişletilmiş öznitelik, tanımlı parantez sınırlayıcıları olan veya olmayan [clsidfromstring](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring)tarafından tanınan dizeleri kabul eder. `uuid`

Aşağıdaki örnek C2778 oluşturur:

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```