---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3218'
title: Derleyici hatası C3218
ms.date: 11/04/2016
f1_keywords:
- C3218
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
ms.openlocfilehash: 9b8b3ed9fdd0fa2632435f4afd9d6ef9bb39b49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173707"
---
# <a name="compiler-error-c3218"></a>Derleyici hatası C3218

' Type ': tür kısıtlama olarak kullanılamaz

Bir türün kısıtlama olması için, bir değer türü veya yönetilen bir sınıfa ya da arabirime başvuru olmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3218 oluşturur.

```cpp
// C3218.cpp
// compile with: /clr /c
class A {};
ref class B {};

// Delete the following 3 lines to resolve.
generic <class T>
where T : A   // C3218
ref class C {};

// OK
generic <class T>
where  T : B
ref class D {};
```
